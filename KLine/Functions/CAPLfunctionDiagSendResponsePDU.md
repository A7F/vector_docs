# DiagSendResponsePDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long DiagSendResponsePDU(BYTE rawPDU[], WORD rawPDULength)
```

## Description

Sends a raw byte buffer. E.g. this allows sending responses with invalid protocol headers.

## Parameters

- **rawPDU**: Byte buffer to be transmitted.
- **rawPDULength**: Length of the byte buffer.

## Return Values

On success 0, otherwise a value less than 0.

## Example

```plaintext
variables
{
   const cTesterAddress = 0xF1;
   const cEcuAddress = 0x86;
}

_Diag_DataRequest( BYTE data[], dword count, long furtherSegments)
{
   long status;
   // Replace Frame
   BYTE FI_Response[6] = { 0x82, cTesterAddress, cEcuAddress, 0x99, 0xff, 0x01 };
   FI_Response[3] = data[0];
   DiagSendResponsePDU( FI_Response, elcount( FI_Response));
   return;
}
```
