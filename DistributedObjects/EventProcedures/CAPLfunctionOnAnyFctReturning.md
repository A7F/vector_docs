[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/EventProcedures/CAPLfunctionOnAnyFctReturning.md)

**CAPL Functions** » **Distributed Objects** » **on any_fct_returning**

# on any_fct_returning

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`on any_fct_returning <provided or internal interface method>;`

## Description

This handler is called whenever a method of a distributed object derived from the given interface is about to return its answer at the provider. At this time, the automatic answering feature has already set the out parameters and return value to their default values if it is configured and the default answer time has elapsed.

The handler is particularly useful if the answer time is determined by another component.

## Parameters

- **<provided or internal interface method>**: Designates the provided or internal interface method for which the handler shall react.

## Selectors

- **object**: Parent object of the called method.
  - Type: `distObjRef <T>`
  - Access Limitation: Read only

- **context**: Call context of the method call.
  - Type: `callContext <T>`
  - Access Limitation: Read only

## Example

```plaintext
// vCDL
version 1.4;
namespace SomeNamespace
{
  interface SomeInterface
  {
    internal method int32 SomeMethod();
  }
  SomeInterface Obj1;
  SomeInterface Obj2;
}

// CAPL
on key 'a'
{
  $Obj1.SomeMethod.DefaultResult = 1;
  Obj1.SomeMethod.CallAsync();
}
on key 'b'
{
  $Obj2.SomeMethod.DefaultResult = 2;
  Obj2.SomeMethod.CallAsync();
}
on any_fct_returning SomeInterface.SomeMethod
{
  write("SomeMethod is returning at object %s with value %d", this.object.Path, this.context.Result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)