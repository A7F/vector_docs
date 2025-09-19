# coTfsClearObjectName

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsClearObjectName( dword nodeId );
```

## Description

This function deletes stored object names that are loaded with [coTfsLoadDeviceDescription](CAPLfunctionCoTfsLoadDeviceDescription.md).

## Parameters

- **nodeId**: Node-ID of the relevant node or 0 if all nodes are used.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* clear known object dictionary entries for node-ID 112 */
if (coTfsClearObjectName(112) != 1)
{
  /* clear process failed */
} /* if */
```
