[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctionBindingCreateCallContext.md)

# Binding::CreateCallContext

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » Binding::CreateCallContext

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

```plaintext
long Binding::CreateCallContext(distObjMethodRef * member, int64 requestID, callContext <Prototype>& cco);
```

## Description

Creates a new call context with the given method member prototype and request ID. The function prototype of the call context must match the function prototype of the method member.

## Parameters

- **member**: Method member which provides the function prototype and call context side.
- **requestID**: Request ID of the call.
- **cco**: Out-parameter for the new call context.

## Return Values

- **0**: OK
- **1**: No CAPL binding configured
- **5**: Wrong or invalid method member

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)