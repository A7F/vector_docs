# on transmit_value

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
on transmit_value <Member>;
```

## Description

This handler is called whenever a provided data, event, or field member transmits a value via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted. Inside the handler, the `this` expression refers to the value of the member (i.e., it is of type `valueHandle <Member type>`).

## Parameters

- **`<Member>`**: Provided data, event or field member.

## Selectors

—

## Example

```plaintext
// transmit an event via CAN messages

// example.vcdl
version 1.3;
namespace SomeNamespace {
  interface Example {
    [Binding="CAPL", CommunicationPattern=SendReceive]
    consumed event int32 SomeEvent;
  }
  object Consumer : Example {}
  object Provider : reverse<Example> {}
}

// provider.can
on key 'a' {
  $Provider.SomeEvent++;
}

// provider_binding.can
on transmit_value Provider.SomeEvent {
  message SomeEvent_Value msg;
  msg.value = $this;
  output(msg);
}

// consumer.can
on value_update Consumer.SomeEvent {
  write("received %d", $this);
}

// consumer_binding.can
on message SomeEvent_Value {
  Binding::ValueReceived(Consumer.SomeEvent, (long)this.value);
}
```
