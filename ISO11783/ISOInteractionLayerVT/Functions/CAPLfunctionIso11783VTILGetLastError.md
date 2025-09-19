[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetLastError.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetLastError**

# VTIL_GetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetLastError(); // form 1`
- `long VTIL_GetLastError(dbNode vt); // form 2`

## Description

Gets the return value of the last called VT IL function.

## Parameters

- **vt**: VT simulation node to apply the function

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
