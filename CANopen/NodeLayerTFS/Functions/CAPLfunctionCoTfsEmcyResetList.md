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
