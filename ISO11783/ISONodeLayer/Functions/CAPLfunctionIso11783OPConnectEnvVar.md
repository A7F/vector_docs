# Iso11783OPConnectEnvVar

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPConnectEnvVar( dword ecuHandle, char envVarName[], dword objectId );
```

## Description

Connects an object (variable, value or string) from the object pool to an environment variable.

If an object is changed, the new value is put in the environment variable. And vice versa, if the value of an environment variable is changed, the new value is also written to the connected object. Additionally, a **Change String** or **Change Numeric Value** command is sent to the Virtual Terminal.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **envVarName**: Name of the environment variable.
- **objectID**: Identifier of the object in the object pool.

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPConnectEnvVar( handle, "EnvSprayer_AppRate", 1040 );
```
