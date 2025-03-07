[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenUploadGetSigned.md)

**Structure Path:** [CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenUploadGetSigned

# CANopenUploadGetSigned

**Valid for:** [CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
Int64 CANopenUploadGetSigned(dword errCode[] );
```

## Description

Returns the data of a CANopen upload in a callback function as a signed value.

## Parameters

- **errCode**: Error code buffer (is entered in index 0 of the field)
  - 0: Value was retrieved
  - 1: Value not available

## Return Values

The data as Int64.

## Example

```c
dword errCode[1];
CANopenUpload ( 1, 0x2000, 0x00, 0, errCode );
if (errCode[0] == 0)
{
  write( "SDO Upload successfully initiated" );
}

void OnCANopenUploadResponse ( dword nodeId, dword index, dword subIndex, dword size )
{
  dword errCode[1];
  Int64 value;
  value = CANopenUploadGetSigned(errCode );
  write( "Upload response data: %I64d", value );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)