# Iso11783GetEnvInt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783GetEnvInt( char[] envVar, dword index );
```

## Description

This function gets the value of an environment variable.

## Parameters

- **envVar**: Name of the environment variable
- **index**: Index of the environment variable

## Return Values

Value of the environment variable or 0 if it does not exist

## Example

```plaintext
value = Iso11783GetEnvInt( "EvFrictionForce", 1 );
```
