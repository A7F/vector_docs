# J1939GetEnvDbl

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double J1939GetEnvDbl( char envVar[], dword index );
```

## Description

This function gets the value of an environment variable.

## Parameters

- **envVar**: name of the environment variable
- **index**: index of the environment variable

## Return Values

Value of the environment variable or 0.0 if it does not exist

## Example

```plaintext
value = J1939GetEnvDbl( "EvFrictionForce", 1 );
```
