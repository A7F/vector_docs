[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783Getlasterrortext.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783GetLastErrorText

# Iso11783GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetLastErrorText( dword bufferSize, char buffer[] );
```

## Description

This function gets the description of the last occurred error.

## Parameters

- **bufferSize**: Size of buffer for error description
- **buffer**: Contains the error description

## Return Values

Number of characters that are copied to **buffer**

## Example

```plaintext
dword size = 100;
char errText[size];

Iso11783GetLastErrorText(size, errText);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
