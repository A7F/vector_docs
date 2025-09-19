# CANopenUploadDomain

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `void CANopenUploadDomain(dword nodeID, dword index, dword subIndex, char[] domainDataFile, dword blockMode, dword[] errCode); // form 1`
- `void CANopenUploadDomain(SysVarName, char[] domainDataFile, dword blockMode, dword[] errCode); // form 2`
- `void CANopenUploadDomain(char[] namespace, char[] variable, char[] domainDataFile, dword blockMode, dword[] errCode); // form 3`
- `void CANopenUploadDomain(dword clientCOBID, dword serverCOBID, dword index, dword subIndex, char[] domainDataFile, dword blockMode, dword[] errCode); // form 4`

## Callback

- `OnCANopenDomainUploadBegin(dword index, dword subindex, dword size);`
- `OnCANopenDomainUploadNextData(dword id, dword index, dword sublndex, dword offset, dword payIoadSize, byte payload[]);`
- `void OnCANopenAbort(dword id, dword index, dword subIndex, dword abortCode);`

## Description

Reads an entry of type DOMAIN from the object dictionary of another node...

- form 1: ... by given node ID.
- form 2, 3: ... by given system variable.
- form 4: ... by given COB-ID.

## Parameters

- **nodeID**: Node ID of the SDO server, i.e. the node that contains the object dictionary with the entry to be read. Value range 1..127
- **clientCOBID**: CAN ID of the SDO client
- **serverCOBID**: CAN ID of the SDO server
- **index**: Index of the object, value range 1..65.535
- **id**: nodeID for form 1-3, serverCOBID for form 4
- **subIndex**: Subindex of the object, value range 0..255
- **domainDataFile**: Path to a file into which the domain data will be written. If empty, the callbacks `CANopenDomainUploadBegin` and `CANopenDomainUloadNextData` will be called.
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
- **abortCode**: SDO abort code.
- **namespace**: Name of the namespace.
- **variable**: Name of the CANopen system variable.
- **SysVarName**: Name of the fully qualified name of the CANopen system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".

## Return Values

—

## Example

—
