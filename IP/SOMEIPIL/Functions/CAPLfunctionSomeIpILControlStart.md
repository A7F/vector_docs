[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpILControlStart.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpILControlStart**

# SomeIpILControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlStart();
```

## Description

Starts SOME/IP IL.

Enabled sending and receiving SOME/IP messages and Service Discovery. After the start of SOME/IP IL, all Application Endpoints and the Provided Services must be created.

SOME/IP IL can be stopped using the [SomeIpILControlStop](CAPLfunctionSomeIpILControlStop.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key '1'
{
  // start IL manually
  SomeIpILControlStart();

  // add application endpoints and provided services here
}
```

[See Also](javascript:void(0);)