# coTfsEmcySendMessage (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsEmcySendMessage( dword nodeID, dword emcyCode, dword errorReg, byte inMsCodeBuf[5], dword msCodeBufSize );
```

## Description

This function sends out an emergency message.

## Parameters

- **nodeID**: Node-ID of the node that is sender of the message.
- **emcyCode**: Emergency code.
- **errorReg**: Error register.
- **inMsCodeBuf[]**: Manufacturer-specific code (data field).
- **msCodeBufSize**: Size of buffer in byte of `inMsCodeBuf`.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pMsCode[5] = {0,0,0,0,0};
if (coTfsEmcySendMessage(112, 0x8220, 0x20, pMsCode, 5) != 1) {
  write("coTfsSendEmcyMessage failed");
}
```
