[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/CANopenBasic/Functions/CAPLfunctionsCANopenDomainServerOpenFileRead.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Basic Functions](../CAPLfunctionsCANopenBasicOverview.md) » CANopenDomainServerOpenFileRead

# CANopenDomainServerOpenFileRead

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```
dword CANopenDomainServerOpenFileRead (dword nodeID, dword index, dword subIndex);
```

## Description

Opens the file for a domain data object of a CANopen node for read access.

## Parameters

- **nodeId**: Node ID of the SDO server, i.e. the node that contains the object dictionary with the domain data entry to be read. Value range 1..127.
- **index**: Index of the object. Value range 1..65,535.
- **subIndex**: Subindex of the object. Value range 0..255.

## Return Values

- The return value is the file handle that must be used for read operations.
- If an error occurs, the return value is **0**.

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)