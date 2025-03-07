[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783Set.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783Set...

# Iso11783Set...

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783SetAAC( char[] deviceName, long aac);`
- `long Iso11783SetIG( char[] deviceName, long ig);`
- `long Iso11783SetVS( char[] deviceName, long vs);`
- `long Iso11783SetVSInstance( char[] deviceName, long vsi);`
- `long Iso11783SetFct( char[] deviceName, long fct);`
- `long Iso11783SetFctInstance( char[] deviceName, long fct);`
- `long Iso11783SetECUInstance( char[] deviceName, long ecui );`
- `long Iso11783SetMC( char[] deviceName, long mc);`
- `long Iso11783SetIN( char[] deviceName, long in);`

## Description

The function modifies a part of the device name.

## Parameters

- **deviceName**: Buffer containing the modified part of the device name, size of 8 bytes required

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)