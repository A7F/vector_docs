[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783GetEnvDbl.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Node Layer** » Iso11783GetEnvDbl

# Iso11783GetEnvDbl

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double Iso11783GetEnvDbl( char envVar[], dword index );
```

## Description

This function gets the value of an environment variable.

## Parameters

- **envVar**: Name of the environment variable
- **index**: Index of the environment variable

## Return Values

Value of the environment variable or 0.0 if it does not exist

## Example

```plaintext
value = Iso11783GetEnvDbl( "EvFrictionForce", 1 );
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
