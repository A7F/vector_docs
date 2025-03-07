[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoResetAbortList.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsSDOResetAbortList**

# coTfsSDOResetAbortList (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

- `long coTfsSDOResetAbortList( dword nodeID ); // form 1`
- `long coTfsSDOResetAbortList( void ); // form 2`

## Description

- **Form 1**: Removes all entries of the previously received SDO abort codes from the internal list. The following call of [coTfsSdoGetAbortCode](CAPLfunctionCoTfsSdoGetAbortCode.md) returns 0.
- **Form 2**: It is possible to omit the parameter `nodeID`. In this case, the internal saved value set with [coTfsSetNodeId()](CAPLfunctionCoTfsSetNodeId.md) is used as node-ID.

## Parameters

- **nodeID**: 0 for all nodes or specific ID for the messages of an individual node.

## Return Values

- [Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
coTfsSDOResetAbortList( 0 );
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)