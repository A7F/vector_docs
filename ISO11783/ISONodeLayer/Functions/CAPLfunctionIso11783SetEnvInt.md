# Iso11783SetEnvInt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783SetEnvInt( char envVar[], dword index, dword value );
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
Iso11783SetEnvInt( "EvFrictionForce", 1, 3 );
```
