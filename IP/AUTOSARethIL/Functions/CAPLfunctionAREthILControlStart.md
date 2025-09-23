# AREthILControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlStart();
```

## Description

Starts AUTOSAR Eth IL.

Enabled sending and receiving SOME/IP messages and Service Discovery. After the start of AUTOSAR Eth IL, all Application Endpoints and the Provided Services must be created.

AUTOSAR Eth IL can be stopped using the [AREthILControlStop](CAPLfunctionAREthILControlStop.md) function.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)
