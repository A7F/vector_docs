[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpILControlStop.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpILControlStop**

# SomeIpILControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlStop();
```

## Description

Stops the SOME/IP IL. Disables sending and receiving SOME/IP messages and Service Discovery. Application-Endpoints and Provided Services will be closed. The SOME/IP IL can be started again using the [SomeIpILControlStart](CAPLfunctionSomeIpILControlStart.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key '2 '
{
  // stop IL manually
  SomeIpILControlStop();
}
```

[See Also](javascript:void(0);)
