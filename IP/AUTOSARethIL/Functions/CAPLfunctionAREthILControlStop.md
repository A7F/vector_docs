[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthILControlStop.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » **AREthILControlStop**

# AREthILControlStop

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlStop();
```

## Description

Stops the AUTOSAR Eth IL.

Disables sending and receiving SOME/IP messages and Service Discovery. Application-Endpoints and Provided Services will be closed.

The AUTOSAR Eth IL can be started again using the [AREthILControlStart](CAPLfunctionAREthILControlStart.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key '2 '
{
  // stop IL manually
  AREthILControlStop();
}
```

[See Also](javascript:void(0);)