[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetLastErrorText.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetLastErrorText**

# TCIL_GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_GetLastErrorText( dword bufferSize, char buffer[] );` // form 1: deprecated with 13
- `long TCIL_GetLastErrorText( char buffer[] );` // form 2
- `long TCIL_GetLastErrorText( dbNode tc,dword bufferSize, char buffer[]);` // form 3: deprecated with 13
- `long TCIL_GetLastErrorText( dbNode tc, char buffer[]);` // form 4

## Description

Returns the result of the last TC IL function as string.

Form 3 and 4 applicable in test module / test unit only.

## Parameters

- **tc**: TC simulation node to apply the function
- **bufferSize**: size of the return buffer
- **buffer**: return buffer

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
