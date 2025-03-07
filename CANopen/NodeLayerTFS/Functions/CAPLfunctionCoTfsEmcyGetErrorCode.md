[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsEmcyGetErrorCode.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsEmcyGetErrorCode**

# coTfsEmcyGetErrorCode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
dword coTfsEmcyGetErrorCode( dword nodeID, dword outCanId[1], dword outTimeStamp[1], dword outEmcyCode[1], dword outErrorReg[1], byte outMsCodeBuf[5], dword msCodeBufSize );
```

## Description

This function transmits as return value the number of received emergency messages for the CANopen® node labeled with `nodeID`.

Each emergency message can only be called up once. The return value contains the number of received messages including the emergency message returned with the function call. All data pointers are only valid if there is at least one message present.

It is possible to omit the `nodeID` parameter. In this case, the internally-stored value set with [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) is used.

## Parameters

- **nodeID**: The function transmits emergency messages from the selected node-ID. If node-ID is set to 0, the messages of all nodes are transmitted.
- **outCanId**: CAN-ID data field.
- **outTimeStamp**: Data field on the time stamp of the transmitted emergency message in ms.
- **outEmcyCode**: Emergency code data field.
- **outErrorReg**: Error register data field.
- **outMsCodeBuf[]**: Manufacturer-specific error code (data field).
- **msCodeBufSize**: Size of buffer in byte of `outMsCodeBuf`.

## Return Values

Number of available emergency messages.

## Example

```plaintext
dword nodeId , pOutCANID[1], pTimeStamp[1], pEmcyCode[1], pErrorReg[1], retValue;
byte pMsgCode[5];
nodeId = 112;

if (coTfsEmcyGetErrorCode(nodeId, pOutCANID, pTimeStamp, pEmcyCode, pErrorReg, pMsgCode, 5) != 0) {
  write("emergency message received");
  write("nodeID=0x%X; CAN ID 0x%X, timestamp=%d, emcyCode = 0x%X, errorRegister = 0x%X", nodeId, pOutCANID[0], pTimeStamp[0], pEmcyCode[0], pErrorReg[0]);
  write("manufacturer specific code = 0x%X %X %X %X %X", pMsgCode[0], pMsgCode[1], pMsgCode[2], pMsgCode[3], pMsgCode[4]);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)