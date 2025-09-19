# diag_DataInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void diag_DataInd (byte rxBuffer [], long count, long sender); // form 1
void diag_DataInd (char target[], byte rxBuffer[], dword count); // form 2
```

## Description

Passes **count** bytes of the transmitter address **sender** from the **rxBuffer** buffer to the diagnostic layer. Alternatively, the transmitter can be identified using its ECU qualifier **target**.

This function is typically called in a transport layer callback after a message, which may be segmented, has been received in its entirety. The transport layer removes all protocol information (segmentation, flow control, etc.) and forwards only the payload data (e.g. the ECU diagnostic response starting at the service ID and including all response parameters) to the diagnostic layer.

## Parameters

- **rxBuffer**: Byte buffer to be passed to the diagnostic layer.
- **sender**: Address of the transmitter from which the diagnostic message was received.
- **count**: Number of bytes to be passed.
- **target**: Qualifier of the responding ECU.

## Return Values

[Error code](../CAPLfunctionsDiagnosticsErrorCode.md)

## Example

See [DoIP_DataInd](CAPLfunctionDoIPDataInd.md)

```plaintext
// This callback shall be called by an example TP layer
TPLayer_ReceivedData( long connectionHandle, byte data[])
{
  char ecuQualifier[20];
  TPLayerGetECUQualifierForHandle(connectionHandle, ecuQualifier);
  diag_DataInd(ecuQualifier, data, elcount(data));
}
```

[Communication Layer Connection / Reference Implementations](../CAPLfunctionsDiagnosticsConnectionCommunicationLayer.md)
