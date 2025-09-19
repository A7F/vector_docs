# Binding::SubscriptionStateReceived

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » Binding::SubscriptionStateReceived

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long Binding::SubscriptionStateReceived(distObjDataRef * member, dword value);
long Binding::SubscriptionStateReceived(distObjEventRef * member, dword value);
long Binding::SubscriptionStateReceived(distObjFieldRef * member, dword value);
```

## Description

Sets the subscription state of a consumed data, event, or field member value that uses the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md) and **PublishSubscribe** communication pattern.

## Parameters

- **member**: Member which receives a subscription state via the CAPL binding.
- **value**: Subscription state to be received.
  - Unsubscribed (0): `Subscribe()` was not yet called (after the last `Unsubscribe()` call).
  - Requested (1): `Subscribe()` was called but no transmissions have occurred (because the receiver may still be unknown or not ready).
  - Subscribed (2): Member will receive new values.

**Note**: One can use the enum `DOMemberSubscription` from the namespace `_SystemDataTypes::SDStates` (see example).

## Return Values

- **0**: OK
- **1**: No CAPL binding configured
- **2**: Wrong communication pattern
- **4**: Invalid subscription state value
- **5**: Other error

## Example

```plaintext
// Transmit a subscription request via CAN.
//
// This example requires a CAN message "SomeData_Request" with a
// signal "Request" and a CAN message "SomeData_Answer" with a
// signal "Answer".

// example.vcdl
version 1.3;
namespace SomeNamespace {
  interface Example {
    [Binding="CAPL", AutoSubscribe=false]
    consumed data int32 SomeData;
  }
  object Consumer : Example {}
  object Provider : reverse<Example> {}
}

// consumer.can
variables {
  using namespace _SystemDataTypes::SDStates;
}
on key 'a' {
  // toggle subscription state
  if ($Consumer.SomeData.SubscriptionState == DOMemberSubscription::Unsubscribed)
    Consumer.SomeData.Subscribe();
  else
    Consumer.SomeData.Unsubscribe();
}

// consumer_binding.can
variables {
  using namespace _SystemDataTypes::SDStates;
}
on transmit_subscribe Consumer.SomeData {
  message SomeData_Request msg;
  Binding::SubscriptionStateReceived(Consumer.SomeData, DOMemberSubscription::Requested);
  msg.Request = DOMemberSubscription::Requested;
  output(msg);
}
on transmit_unsubscribe Consumer.SomeData {
  message SomeData_Request msg;
  msg.Request = DOMemberSubscription::Unsubscribed;
  output(msg);
}
on message SomeData_Answer {
  Binding::SubscriptionStateReceived(Consumer.SomeData, this.Answer);
}

// provider.can
on key 'b' {
  $Provider.SomeData++;
}

// provider_binding.can
variables {
  using namespace _SystemDataTypes::SDStates;
  enum DOMemberSubscription consumerState;
}
on message SomeData_Request {
  message SomeData_Answer msg;
  consumerState = this.Request == DOMemberSubscription::Requested ?
  DOMemberSubscription::Subscribed :
  DOMemberSubscription::Unsubscribed;
  msg.Answer = consumerState;
  output(msg);
}
on transmit_value Provider.SomeData {
  // value not transmitted via CAN, just set it directly
  if (consumerState == DOMemberSubscription::Subscribed)
    Binding::ValueReceived(Consumer.SomeData, $this);
}
```
