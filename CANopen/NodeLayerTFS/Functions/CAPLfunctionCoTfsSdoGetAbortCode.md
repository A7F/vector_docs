[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSdoGetAbortCode.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSDOGetAbortCode

# coTfsSDOGetAbortCode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOGetAbortCode( dword nodeID, dword outSrcNodeId[1], qword outTimeStamp[1], dword outIndex[1], dword outSubIndex[1], dword outAbortCode[1] ); // form 1
long coTfsSDOGetAbortCode( dword outSrcNodeId[1], qword outTimeStamp[1], dword outIndex[1], dword outSubIndex[1], dword outAbortCode[1] ); // form 2
```

## Description

This function returns received SDO abort codes. In addition, the following information is delivered:

- CAN identifier of the abort message
- time stamp
- index/subindex

Via the parameter **nodeID**, the returned SDO abort codes can be filtered. The value **nodeID=0** returns all SDO abort codes that occur. All SDO abort codes can only be read out once with this function.

(2) It is possible to omit the parameter **nodeID**. In this case, the internal saved value set with [coTfsSetNodeId()](CAPLfunctionCoTfsSetNodeId.md) is used as node-ID.

## Parameters

- **nodeID**: Node-ID of the node whose SDO abort codes should be read out, 0 for all nodes.
- **outSrcNodeId[]**: Pointer to the received CAN-ID.
- **outTimeStamp[]**: CANoe time stamp of the input of the SDO abort code.
- **outIndex[]**: Object index
- **outSubIndex[]**: Object subindex
- **outAbortCode[]**: SDO abort code.

## Return Values

If no SDO abort code was received, the function returns the return value 0.

Otherwise, the number of still-outstanding SDO abort codes (current SDO abort code is contained in this number) is returned. For a return value 0, all return arrays are invalid.

## Example

```plaintext
dword pNodeId[1], pIndex[1], pSubIndex[1], pAbortCode[1];
qword pNanoSecondsTime[1];
dword counter;

if ((counter = coTfsSDOGetAbortCode( pNodeId, pNanoSecondsTime, pIndex, pSubIndex, pAbortCode))!=0) {
  write("SDO abort message caught: counter %d, node-ID 0x%x, time %I64d [ns], index 0x%x, subIndex 0x%x, abortcode 0x%x", counter, pNodeId[0], pNanoSecondsTime[0], pIndex[0], pSubIndex[0], pAbortCode[0]);
}
else {
  write("no SDO abort code received");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)