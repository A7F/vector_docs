[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetLastErrorText.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_GetLastErrorText

# VTIL_GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetLastErrorText( dword bufferSize, char buffer[] ); // form 1: deprecated.`
- `long VTIL_GetLastErrorText( char buffer[] ); // form 2`
- `long VTIL_GetLastErrorText( dbNode vt, dword bufferSize, char buffer[]); // form 3: deprecated.`
- `long VTIL_GetLastErrorText( dbNode vt, char buffer[]); // form 4`

## Description

Returns the result of the last VT IL function as string.

## Parameters

- **vt**: VT simulation node to apply the function
- **bufferSize**: size of the return buffer
- **buffer**: return buffer

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)