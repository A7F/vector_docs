# on transmit_call

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
on transmit_call <Member>;
```

## Description

This handler is called whenever a consumed method member transmits a value via the [CAPL binding](../../../CANoeCANalyzer/CommunicationConcept/CCDOCAPLBinding.md).

If the member does not use the CAPL binding, the handler is ignored.

If there are multiple handlers for the same member, the measurement will be aborted. Inside the handler the this expression refers to the call context of the call (i.e. it is of type callContext `<Member>`).

## Parameters

- **`<Member>`**: Consumed method member.

## Selectors

—

## Example

```plaintext
// Transmit a method call via CAN messages.
// This example requires a CAN message "SomeMethod_Call" with
// signals "x", "y", and "RequestID" as well as a CAN
// message "SomeMethod_Return" with signals "y", "z", "Result",
// and "RequestID".

// example.vcdl
version 1.3;
namespace SomeNamespace {
  interface Example {
    [Binding="CAPL"]
    consumed method int32 SomeMethod(in int32 x, inout int32 y, out int32 z);
  }
  object Consumer : Example {}
  object Provider : reverse<Example> {}
}

// consumer.can
on key 'a' {
  long x, y;
  Consumer.SomeMethod.CallAsync(x++, y--);
}

// consumer_binding.can
on transmit_call Consumer.SomeMethod {
  message SomeMethod_Call msg;
  msg.x = this.x;
  msg.y = this.y;
  msg.RequestID = this.ReqID;
  output(msg);
}
on message SomeMethod_Return {
  callContext Consumer.SomeMethod cco;
  Binding::CreateCallContext(Consumer.SomeMethod, this.RequestID, cco);
  cco.y = this.y;
  cco.z = this.z;
  cco.Result = this.ReturnValue;
  Binding::ReturnReceived(Consumer.SomeMethod, cco);
}

// provider.can
on fct_Called Provider.SomeMethod {
  this.z = 2*this.x;
  this.Result = 2*this.y;
}

// provider_binding.can
on message SomeMethod_Call {
  callContext Provider.SomeMethod cco;
  Binding::CreateCallContext(Provider.SomeMethod, this.RequestID, cco);
  cco.x = this.x;
  Binding::SetInParameter(cco, "y", (long)this.y);
  Binding::CallReceived(Provider.SomeMethod, cco);
}
on transmit_return Provider.SomeMethod {
  message SomeMethod_Return msg;
  msg.RequestID = this.ReqID;
  msg.y = this.y;
  msg.z = this.z;
  msg.ReturnValue = this.Result;
  output(msg);
}
```
