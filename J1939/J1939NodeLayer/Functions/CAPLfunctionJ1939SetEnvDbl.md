[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939SetEnvDbl.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939SetEnvDbl

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

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)