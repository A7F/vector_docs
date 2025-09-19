# CANopenDownload

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `void CANopenDownload( dword nodeId, dword index, dword subIndex, qword data, dword dataSize, dword blockMode, dword errCode[] ); // form 1`
- `void CANopenDownload( dword nodeId, dword index, dword subIndex, char[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 2`
- `void CANopenDownload( dword nodeId, dword index, dword subIndex, byte[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 3`
- `void CANopenDownload( dword nodeId, dword index, dword subIndex, float data, dword 64bit, dword blockMode, dword errCode[] ); // form 4`
- `void CANopenDownload( dword clientCOBID, dword serverCOBID, dword index, dword subIndex, qword data, dword dataSize, dword blockMode, dword errCode[] ); // form 5`
- `void CANopenDownload( dword clientCOBID, dword serverCOBID, dword index, dword subIndex, char[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 6`
- `void CANopenDownload( dword clientCOBID, dword serverCOBID, dword index, dword subIndex, byte[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 7`
- `void CANopenDownload( dword clientCOBID, dword serverCOBID, dword index, dword subIndex, float data, dword 64bit, dword blockMode, dword errCode[] ); // form 8`
- `void CANopenDownload( char[] namespace, char[] variable, qword data, dword dataSize, dword blockMode, dword errCode[] ); // form 9`
- `void CANopenDownload( char[] namespace, char[] variable, char[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 10`
- `void CANopenDownload( char[] namespace, char[] variable, byte[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 11`
- `void CANopenDownload( char[] namespace, char[] variable, float data, dword is64bit, dword blockMode, dword errCode[] ); // form 12`
- `void CANopenDownload( SysVarName, qword data, dword dataSize, dword blockMode, dword errCode[] ); // form 13`
- `void CANopenDownload( SysVarName, char[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 14`
- `void CANopenDownload( SysVarName, byte[] data, dword dataSize, dword blockMode, dword errCode[] ); // form 15`
- `void CANopenDownload( SysVarName, float data, dword is64bit, dword blockMode, dword errCode[] ); // form 16`

## Callback

- `void OnCANopenDownloadResponse(dword id, dword index, dword subIndex, dword size)`
- `void OnCANopenAbort(dword id, dword index, dword subIndex, dword abortCode)`

## Description

Writes an entry in the object dictionary of another node using the SDO protocol. If the data transfer is aborted, the callback `OnCANopenAbort` is called.

## Parameters

- **nodeID**: CANopen node ID of the SDO server, i.e. the node that contains the object dictionary with the entry to be changed. Value range 1..127
- **clientCOBID**: CAN ID of the SDO client
- **serverCOBID**: CAN ID of the SDO server
- **index**: Index of the object, value range 1..65,535
- **subIndex**: Subindex of the object, value range 0..255
- **data**: Data to be written
- **dataSize**: Size of the data in bytes
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
- **id**: nodeId for form 1-4, serverCOBID for form 5-8
- **abortCode**: SDO abort code.
- **namespace**: Name of the namespace.
- **variable**: Name of the CANopen system variable.
- **SysVarName**: Name of the fully qualified name of the CANopen system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **Is64bit**:
  - 0: data is a 32bit float, i.e. 4 bytes will be downloaded
  - 1: data is a 64bit float, i.e. 8 bytes will be downloaded

## Return Values

—

## Example

```c
dword errCode[1];
char data[256] = "DownloadData";

CANopenDownload( 1, 0x2000, 0x00, data, strlen(data), 0, errCode );
if (errCode[0] == 0)
{
  write( "SDO Download successfully initiated" );
}
```
