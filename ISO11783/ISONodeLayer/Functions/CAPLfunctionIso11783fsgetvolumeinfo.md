[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783fsgetvolumeinfo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783FSGetVolumeInfo

# Iso11783FSGetVolumeInfo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783FSGetVolumeInfo( dword infoCount, dword retInfo[] );
```

## Description

This function returns information about the current volume. The current volume is the volume where the configuration is stored.

## Parameters

- **infoCount**: Number of elements in `retInfo`
- **retInfo**: The information about the volume is returned in this array.

  - **Index 0**: bit filled with valid elements, Bit 1 set = Index 1 is valid, ...
  - **Index 1**: total space of the volume in 512 byte blocks
  - **Index 2**: free space in 512 byte blocks

## Return Values

0 or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```plaintext
dword info[3];

Iso11783FSGetVolumeInfo( elCount(info), info );
write( "Total size %d blocks", info[1] );
write( "Free size %d blocks", info[2] );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)