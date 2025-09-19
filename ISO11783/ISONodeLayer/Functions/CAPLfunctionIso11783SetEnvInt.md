[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783SetEnvInt.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783SetEnvInt

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

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
