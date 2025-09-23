[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILGetLastErrorText.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_GetLastErrorText**

# FSIL_GetLastErrorText

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_GetLastErrorText( dword bufferSize, char buffer[] );` // form 1: deprecated with 13
- `long FSIL_GetLastErrorText( char buffer[] );` // form 2
- `long FSIL_GetLastErrorText( dbNode fs, dword bufferSize, char buffer[]);` // form 3: deprecated with 13
- `long FSIL_GetLastErrorText( dbNode fs, char buffer[]);` // form 4

## Description

- Returns the textual description of the value of the last called FS IL function.
- Returns the result of the last FS IL function as string.
- Form 3 and 4 applicable in test module / test unit only.

## Parameters

- **fs**: FS simulation node to apply the function
- **bufferSize**: size of the return buffer
- **buffer**: return buffer

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
