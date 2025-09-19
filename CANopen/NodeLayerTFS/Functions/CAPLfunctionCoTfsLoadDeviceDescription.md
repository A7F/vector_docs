# coTfsLoadDeviceDescription

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLoadDeviceDescription( dword nodeId, char fileName[] );
```

## Description

This function reads an EDS, DCF or XML file. This allows the interpretation of index and subindex during SDO accesses, so that object names can be displayed in plain text.

The object names can be deleted with [coTfsClearObjectName](CAPLfunctionCoTfsClearObjectName.md).

## Parameters

- **nodeId**: Node-ID of the relevant node or 0 if all nodes are used. If node specific entries should be added, these have a higher priority on display.
- **fileName[]**: Name of the file to be read, relative to your CANoe configuration.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* load for CANopen device with node ID 112 the eds file "coslave.eds" (path is relative to configuration folder) */
if (coTfsLoadDeviceDescription(112, "coslave.eds") != 1)
{
  /* file could not be loaded, either it does not exist or it is faulty */
} /* if */
```
