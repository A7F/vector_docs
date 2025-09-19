# CANopenDomainServerSetFileContents

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenDomainServerSetFileContents (dword nodeID, dword index, dword subIndex, char[] filename, dword[] errCode);
```

## Description

Sets the contents of a domain data object file of a CANopen node.

## Parameters

- **nodeId**: Node ID of the SDO server, i.e. the node that contains the object dictionary with the domain data entry to be read. Value range 1..127.
- **index**: Index of the object. Value range 1..65,535.
- **subIndex**: Subindex of the object. Value range 0..255.
- **filename**: Name of the file which will be used for the domain data entry.
- **errCode**:
  - 0: Ok.
  - 1: No file selected for the domain data object in the CANopen Setup window.
  - 2: Object entry does not exist.
  - 3: The file does not exist or cannot be opened.

## Return Values

—

## Example

—
