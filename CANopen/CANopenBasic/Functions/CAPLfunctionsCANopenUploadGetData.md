[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenUploadGetData.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenUploadGetData

# CANopenUploadGetData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
void CANopenUploadGetData( char[] buffer, dword bufferSize, dword errCode[] ); //form 1
void CANopenUploadGetData( byte[] buffer, dword bufferSize, dword errCode[] ); //form 2
```

## Description

Returns the data of a CANopen upload in a callback function as char or byte array.

## Parameters

- **buffer**: Char (form 1) or byte (form 2) array buffer for the data.
- **bufferSize**: Size of the buffer in bytes.
- **errCode**: Error code buffer (is entered in index 0 of the field).
  - 0: Value was retrieved
  - 1: Value not available

## Return Values

—

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
  char value[100];
  CANopenUploadGetData ( value, elcount(value), errCode );
  write( "Upload response data: %s", value );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)