# CANopenUploadGetUnsigned

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
qword CANopenUploadGetUnsigned(dword errCode[] );
```

## Description

Returns the data of a CANopen upload in a callback function as an unsigned value.

## Parameters

- **errCode**: Error code buffer (is entered in index 0 of the field)
  - 0: Value was retrieved
  - 1: Value not available

## Return Values

The data as qword.

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
  qword value;
  value = CANopenUploadGetUnsigned(errCode );
  write( "Upload response data: %I64u", value );
}
```
