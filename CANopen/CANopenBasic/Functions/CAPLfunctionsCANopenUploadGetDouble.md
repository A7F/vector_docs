[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenUploadGetDouble.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenUploadGetDouble

# CANopenUploadGetDouble

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
float CANopenUploadGetDouble(dword errCode[] );
```

## Description

Returns the data of a CANopen upload in a callback function as double.

## Parameters

- **errCode**: Error code buffer (is entered in index 0 of the field)
  - 0: Value was retrieved
  - 1: Value not available

## Return Values

The data as float.

## Example

```plaintext
dword errCode[1];
CANopenUpload ( 1, 0x2000, 0x00, 0, errCode );
if (errCode[0] == 0)
{
  write( "SDO Upload successfully initiated" );
}

void OnCANopenUploadResponse ( dword nodeId, dword index, dword subIndex, dword size )
{
  dword errCode[1];
  float value;
  value = CANopenUploadGetDouble (errCode );
  write( "Upload response data: %f", value );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)