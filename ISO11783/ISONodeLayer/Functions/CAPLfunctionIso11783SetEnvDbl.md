# Iso11783SetEnvDbl

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783SetEnvDbl( char envVar[], dword index, float value );
```

## Description

This function sets the value of an environment variable.

## Parameters

- **envVar**: Name of the environment variable
- **index**: Index of the environment variable
- **value**: New value

## Return Values

0 on success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783SetEnvDbl( "EvFrictionForce", 1, 33.12 );
```
