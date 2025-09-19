[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939Set.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939Set...

# J1939Set...

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939SetAAC( char[] deviceName, long aac)`
- `long J1939SetIG( char[] deviceName, long ig)`
- `long J1939SetVS( char[] deviceName, long vs)`
- `long J1939SetVSInstance( char[] deviceName, long vsi)`
- `long J1939SetFct( char[] deviceName, long fct)`
- `long J1939SetFctInstance( char[] deviceName, long fct)`
- `long J1939SetECUInstance( char[] deviceName, long ecui )`
- `long J1939SetMC( char[] deviceName, long mc)`
- `long J1939SetIN( char[] deviceName, long in)`

## Description

The function modifies a part of the device name.

## Parameters

- **deviceName**: buffer containing the modified part of the device name, size of 8 bytes required

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
