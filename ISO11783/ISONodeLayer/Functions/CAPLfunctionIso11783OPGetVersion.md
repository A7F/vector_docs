[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPGetVersion.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPGetVersion

# Iso11783OPGetVersion

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetVersion( dword ecuHandle );
long Iso11783OPGetVersion( dword ecuHandle, byte extendedVersions );
```

## Description

The function requests the stored object pools from the Virtual Terminal. A **Get Version** command or a **Get Extended Version** command is sent to the Virtual Terminal. If a response from the Virtual Terminal is received, the callback function [Iso11783OPOnResponse](CAPLfunctionIso11783OPOnResponse.md) is called.

## Parameters

- **ecuHandle**: Handle of the ECU (must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md))
- **extendedVersions**: Kind of versions to query.
  - To get extended versions a [VT version](CAPLfunctionIso11783OPSetProperty.md) 5 or higher is necessary.
  - 0: get standard version strings (7 characters)
  - 1: get extended version strings (32 characters)

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
Iso11783OPGetVersion(handle);

[...]

void Iso11783OPOnResponse( dword handle, pg VTtoECU response ) {
  switch(response.BYTE(0)) {
    case 224:
      // handle GetVersion response here
      break;
    case 211:
      // handle Get Extended Version response here
      break;
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)