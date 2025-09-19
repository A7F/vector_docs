[J1939GetEnvDbl](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939GetEnvDbl.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939GetEnvDbl

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
