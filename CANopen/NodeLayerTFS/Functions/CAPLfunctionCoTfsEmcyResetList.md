[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsEmcyResetList.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsEmcyResetList

# coTfsEmcyResetList (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsEmcyResetList( void );
long coTfsEmcyResetList( dword nodeID );
```

## Description

This function deletes the internal list on which occurring emergency messages are stored.

It is possible to omit the **nodeID** parameter. In this case, the internally-stored value set with [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) is used.

## Parameters

- **nodeID**: All messages of the associated node-ID are deleted; for `nodeID=0`, all emergency messages of all nodes are deleted.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsEmcyResetList(2);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)