[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsClearObjectName.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsClearObjectName

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)