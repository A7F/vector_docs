[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939Get.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939Get...**

# J1939Get...

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939GetAAC( char[] deviceName )`
- `long J1939GetIG( char[] deviceName )`
- `long J1939GetVS( char[] deviceName )`
- `long J1939GetVSInstance( char[] deviceName )`
- `long J1939GetFct( char[] deviceName )`
- `long J1939GetFctInstance( char[] deviceName )`
- `long J1939GetECUInstance( char[] deviceName )`
- `long J1939GetMC( char[] deviceName )`
- `long J1939GetIN( char[] deviceName )`

## Description

This function reads a part of the device name.

## Parameters

- **deviceName**: buffer for read part of the device name, minimum size of 8 bytes required

## Return Values

Value of the device name part

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
