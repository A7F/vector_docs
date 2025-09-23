# J1939SetEnvDbl

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939SetEnvDbl( char envVar[], dword index, float value );
```

## Description

This function sets the value of an environment variable.

## Parameters

- **envVar**: name of the environment variable
- **index**: index of the environment variable
- **value**: new value

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```plaintext
J1939SetEnvDbl( "EvFrictionForce", 1, 33.12 );
```
