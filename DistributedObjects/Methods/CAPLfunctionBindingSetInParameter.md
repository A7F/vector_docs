[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctionBindingSetInParameter.md)

# Binding::SetInParameter

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » Binding::SetInParameter

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

- `long Binding::SetInParameter(callContext * cco, char name[], double value);`
- `long Binding::SetInParameter(callContext * cco, char name[], long value);`
- `long Binding::SetInParameter(callContext * cco, char name[], dword value);`
- `long Binding::SetInParameter(callContext * cco, char name[], int64 value);`
- `long Binding::SetInParameter(callContext * cco, char name[], qword value);`
- `long Binding::SetInParameter(callContext * cco, char name[], char value[]);`
- `long Binding::SetInParameter(callContext * cco, char name[], dataTypeHandle value);`

## Description

Sets the value of an in-parameter. It is required because the normal assignment for inout-parameters only writes to the out-value. The called overload must correspond to the parameter type.

## Parameters

- **cco**: Call context where the parameter shall be set.
- **name**: Name of the parameter.
- **value**: Value of the parameter.

## Return Values

- **0**: OK
- **4**: Parameter not found
- **5**: Wrong parameter type

## Example

```plaintext
// Transmit a method call via CAN messages.
// This example requires a CAN message "SomeMethod_Call" with
// signals "x", "y", and "RequestID" as well as a CAN
// message "SomeMethod_Return" with signals "y", "z", "Result",
// and "RequestID"

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

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)