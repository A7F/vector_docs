[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetVersion.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPGetVersion

# Iso11783IL_OPGetVersion

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPGetVersion();` // form 1
- `long Iso11783IL_OPGetVersion(byte extendedVersions);` // form 2
- `long Iso11783IL_OPGetVersion(dbNode implement, byte extendedVersions);` // form 3

## Description

The function requests the stored object pools from the Virtual Terminal. A **Get Versions** command or a **Extended Get Versions** command is sent to the Virtual Terminal. If a response from the Virtual Terminal is received, the callback function [Iso11783IL_OPOnResponse](CAPLfunctionIso11783ILOPOnResponse.md) is called.

## Parameters

- **extendedVersions**: kind of versions to query.
  - To get extended versions a [VT version](CAPLfunctionIso11783ILOPSetProperty.md) 5 or higher is necessary.
  - 0: get standard version strings (7 characters)
  - 1: get extended version strings (32 characters)

- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPGetVersion();

[...]

void Iso11783IL_OPOnResponse(dword handle, pg VTtoECU response) {
  switch(response.BYTE(0)) {
    case 224:
      // handle GetVersions response here
      break;
    case 211:
      // handle Extended Get Versions response here
      break;
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
