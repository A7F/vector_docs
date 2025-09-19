# AfdxIsReceiveCallbackRegistered

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxIsReceiveCallbackRegistered( char callback[] );
```

## Description

Use this function to check if a callback with this name is already installed with [AfdxRegisterReceiveCallback](CAPLfunctionAfdxRegisterReceiveCallback.md).

## Parameters

- **callback**: Name of CAPL callback to check.

## Return Values

- **0**: not installed
- **1**: installed
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

—
