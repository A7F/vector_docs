# AfdxDeregisterReceiveCallback

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxDeregisterReceiveCallback( char callback[] );
```

## Description

Use this function to deregister a CAPL callback that has been registered with [AfdxRegisterReceiveCallback](CAPLfunctionAfdxRegisterReceiveCallback.md).

## Parameters

- **callback**: Name of CAPL callback to be deregistered.

## Return Values

- **0**: Success
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

—
