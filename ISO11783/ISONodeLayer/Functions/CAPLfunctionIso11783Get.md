[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783Get.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783Get...

# Iso11783Get...

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783GetAAC( char[] deviceName );`
- `long Iso11783GetIG( char[] deviceName );`
- `long Iso11783GetVS( char[] deviceName );`
- `long Iso11783GetVSInstance( char[] deviceName );`
- `long Iso11783GetFct( char[] deviceName );`
- `long Iso11783GetFctInstance( char[] deviceName );`
- `long Iso11783GetECUInstance( char[] deviceName );`
- `long Iso11783GetMC( char[] deviceName );`
- `long Iso11783GetIN( char[] deviceName );`

## Description

This function reads a part of the device name.

## Parameters

- **deviceName**: Buffer for read part of the device name, minimum size of 8 bytes required

## Return Values

Value of the device name part

## Example

—

© Vector Informatik GmbH
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)