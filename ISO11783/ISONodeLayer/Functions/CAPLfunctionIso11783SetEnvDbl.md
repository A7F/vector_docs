[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783SetEnvDbl.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783SetEnvDbl

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)