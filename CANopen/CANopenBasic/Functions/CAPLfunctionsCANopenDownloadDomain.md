[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenDownloadDomain.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenDownloadDomain

# CANopenDownloadDomain

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `void CANopenDownloadDomain(dword nodeID, dword index, dword subIndex, dword dataSize, dword blockMode, dword errCode); // form 1`
- `void CANopenDownloadDomain(SysVarName, dword dataSize, dword blockMode, dword[] errCode); // form 2`
- `void CANopenDownloadDomain(char[] namespace, char[] variable, dword dataSize, dword blockMode, dword[]errCode); // form 3`
- `void CANopenDownloadDomain(dword clientCOBID, dword serverCOBID, dword index, dword subIndex, dword dataSize, dword flags, dword[]errCode); // form 4`

## Callback

- `OnCANopenDomainDownloadNextData(dword id, dword index, dword subindex, dword offset, dword payloadSize, byte payload[]);`
- `void OnCANopenAbort(dword id, dword index, dword subIndex, dword abortCode);`

## Description

Writes an entry of type DOMAIN from the object dictionary of another node...

- form 1: ... by given node ID
- form 2, 3: ... by given system variable.
- form 4: ... by given COB-ID.

## Parameters

- **nodeID**: Node ID of the SDO server, i.e. the node that contains the object dictionary with the entry to be changed. Value range 1..127.
- **clientCOBID**: CAN ID of the SDO client.
- **serverCOBID**: CAN ID of the SDO server.
- **index**: Index of the object, value range 1..65.535.
- **subIndex**: Subindex of the object, value range 0..255.
- **dataSize**: Size of the data in bytes.
- **blockMode**:
  - 0: Use expedited or segmented data transfer
  - 1: Use block data transfer
- **errCode**: Error code buffer (is entered in index 0 of the field):
  - 0: Operation can be started
  - 1: Operation already running
  - 3: Invalid Client-COBID
  - 4: Invalid Server-COBID
  - 5: No CANopen license
  - 6: No CAN channel
- **id**: nodeId for form 1-3, serverCOBID for form 4.
- **abortCode**: SDO abort code.
- **namespace**: Name of the namespace.
- **variable**: Name of the CANopen system variable.
- **SysVarName**: Name of the fully qualified name of the CANopen system variable, including all namespaces, separated by "::". The name must be preceded by "sysVar::".
- **payloadSize**: Size of the payload in bytes.
- **payload**: Data to be written.

## Return Values

—

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)