[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctiondistObjMethodRefCall.md)

**CAPL Functions** » [Distributed Objects](../CAPLfunctionsDOOverview.md) » distObjMethodRef::Call

# distObjMethodRef::Call

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

`<Method Return Type> distObjMethodRef::Call (params ...);`

## Description

Synchronous call to a method member, i.e. the call waits for the function to be called and the return to be received.

## Parameters

The **in**, **inout**, and **out** parameters of the method. The function expects the arguments in **impl** encoding. Arguments to **inout** and **out** parameters must be lvalues (except for string literals, which are lvalues but not allowed in this context).

## Return Values

The returned value of the actual call to the method member.

## Example

```plaintext
on start
{
  distObjRef ExampleInterface object = ExampleObject;
  int Result;
  Result = object.ExampleMethod.Call(1, 2);
  write("Result = %d", Result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)