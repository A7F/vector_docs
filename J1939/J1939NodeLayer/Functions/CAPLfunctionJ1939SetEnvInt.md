# J1939SetEnvInt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939SetEnvInt( char envVar[], dword index, dword value );
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

```c
J1939SetEnvInt( "EvFrictionForce", 1, 3 );
```
