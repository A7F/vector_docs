[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPGetVTInfo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPGetVTInfo

# Iso11783OPGetVTInfo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783OPGetVTInfo( dword ecuHandle, char key[] );
```

## Description

During initialization phase the Object Pool API request some information about the capabilities from Virtual Terminal. These information can be get with this function.

## Parameters

- **ecuHandle**: Handle of the ECU. The handle must be created with [Iso11783CreateECU](CAPLfunctionIso11783CreateECU.md).
- **key**: Key of information:
  - "VersionNumber": Get memory
  - "NavigationSoftKeyCount": Get number of Soft Keys
  - "SoftKeyWidth": Get width of Soft Keys
  - "SoftKeyHeight": Get height of Soft Keys
  - "VirtualSoftKeyCount": Get number of virtual Soft Keys
  - "PhysicalSoftKeyCount": Get number of physical Soft Keys
  - "SmallFontSizes": Get Text Font Data
  - "LargeFontSizes": Get Text Font Data
  - "FontTypeAttribute": Get Text Font Data
  - "BootTime": Get Hardware
  - "GraphicType": Get Hardware
  - "Hardware": Get Hardware
  - "Width": Get Hardware
  - "Height": Get Hardware

## Return Values

- **≥ 0**: value
- **< 0**: an error has occurred, see [error codes](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
LONG vtWidth;
vtWidth = Iso11783OPGetVTInfo( handle, "Width" );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)