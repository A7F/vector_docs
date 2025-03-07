[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenUpload.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenUpload

# CANopenUpload

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `void CANopenUpload( dword id, dword index, dword subIndex, dword blockMode, dword errCode[] ); // form 1`
- `void CANopenUpload( dword clientCOBID, dword serverCOBID, dword index, dword subIndex, dword blockMode, dword errCode[] ); // form 2`
- `void CANopenUpload( char[] namespace, char[] variable, dword blockMode, dword errCode[] ); // form 3`
- `void CANopenUpload( SysVarName, dword blockMode, dword errCode[] ); // form 4`

## Callback

- `void OnCANopenUploadResponse(dword id, dword index, dword subIndex, dword size)`
- `void OnCANopenAbort(dword nodeId, dword index, dword subIndex, dword abortCode)`

## Description

Reads an entry from the object dictionary of another node using the SDO protocol. When the node responds with the requested data, the callback `OnCANopenUploadResponse` is called. If the data transfer is aborted, the callback `OnCANopenAbort` is called.

## Parameters

- **nodeID**: CANopen node ID of the SDO server, i.e. the node that contains the object dictionary with the entry to be read. Value range 1..127
- **id**: nodeId for form 1, serverCOBID for form 2
- **clientCOBID**: CAN ID of the SDO client
- **serverCOBID**: CAN ID of the SDO server
- **index**: Index of the object, value range 1..65.535
- **subIndex**: Subindex of the object, value range 0..255
- **size**: Size of the data in bytes
- **blockMode**:
  - 0: Use expedited or segmented data transfer
  - 1: Use block data transfer
- **errCode**: Error code buffer (is entered in index 0 of the field)
  - 0: Operation can be started
  - 1: Operation already running
  - 3: Invalid Client-COBID
  - 4: Invalid Server-COBID
  - 5: No CANopen license
  - 6: No CAN channel
- **namespace**: Name of the namespace.
- **variable**: Name of the CANopen system variable.
- **SysVarName**: Name of the fully qualified name of the CANopen system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

—

## Example

```c
dword errCode[1];
CANopenUpload ( 1, 0x1000, 0x00, 0, errCode );

if (errCode[0] == 0)
{
  write( "SDO Upload successfully initiated" );
}

void OnCANopenUploadResponse ( dword nodeId, dword index, dword subIndex, dword size )
{
  dword errCode[1];
  dword value;
  value = CANopenUploadGetUnsigned ( errCode );
  write( "Upload response data: 0x%X", value );
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)