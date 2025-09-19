# AfdxGetSignalString

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxGetSignalString

## Valid for:
- CANoe DE
- CANoe:lite DE
- CANoe4SW DE
- CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetSignalString( long packet, char signalName[], long bufSize, char buffer[] ); // form 1
long AfdxGetSignalString( long packet, long offset, long bufSize, char buffer[] ); // form 2
```

## Description

This function copies up to **bufSize** characters of an AFDX string to the specified buffer. The AFDX string structure consists of a 16-bit length code n and a sequence of n ASCII characters.

## Parameters

- **packet**: Handle of the message.
- **signalName**: Name of the signal.  
  **Note:** The signal and the message need to be defined in the assigned DBC file.
- **offset**: The offset value points to the starting byte of the AFDX string.
- **bufSize**: Size of available buffer area.
- **buffer**: Buffer containing the read string value.

## Return Values

- Number of copied data bytes.
- If this value is > **bufSize** an error occurred.

## Example

—

## See Also

- [Feature availability for your product](../../../Shared/FeatureAvailability.md)
- [AFDX CAPL Functions](../CAPLfunctionsAFDXOverview.md)
- [AFDX Error Codes](../CAPLfunctionsAFDXErrorCodes.md)
- [AfdxCompletePacket](CAPLfunctionAfdxCompletePacket.md)
- [AfdxDeregisterReceiveCallback](CAPLfunctionAfdxDeregisterReceiveCallback.md)
- [AfdxGetDBAttrAsString](CAPLfunctionAfdxGetDBAttrAsString.md)
- [AfdxGetDBAttrValue](CAPLfunctionAfdxGetDBAttrValue.md)
- [AfdxGetDBMessageName](CAPLfunctionAfdxGetDBMessageName.md)
- [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md)
- [AfdxGetLastErrorText](CAPLfunctionAfdxGetLastErrorText.md)
- [AfdxGetMessageId](CAPLfunctionAfdxGetMessageId.md)
- [AfdxGetMessageName](CAPLfunctionAfdxGetMessageName.md)
- [AfdxGetPacketData](CAPLfunctionAfdxGetPacketData.md)
- [AfdxGetSignalBool](CAPLfunctionAfdxGetSignalBool.md)
- [AfdxGetSignalInt](CAPLfunctionAfdxGetSignalInt.md)
- [AfdxGetSignalInt64](CAPLfunctionAfdxGetSignalInt64.md)
- [AfdxGetSignalOpaque](CAPLfunctionAfdxGetSignalOpaque.md)
- [AfdxGetSignalReal](CAPLfunctionAfdxGetSignalReal.md)
- [AfdxGetSignalStatus](CAPLfunctionAfdxGetSignalStatus.md)
- [AfdxGetSignalString](#aanchor6409)
- [AfdxGetTokenData](CAPLfunctionAfdxGetTokenData.md)
- [AfdxGetTokenInt](CAPLfunctionAfdxGetTokenInt.md)
- [AfdxGetTokenInt64](CAPLfunctionAfdxGetTokenInt64.md)
- [AfdxGetTokenLengthBit](CAPLfunctionAfdxGetTokenLengthBit.md)
- [AfdxGetTokenReal](CAPLfunctionAfdxGetTokenReal.md)
- [AfdxGetTokenString](CAPLfunctionAfdxGetTokenString.md)
- [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)
- [AfdxInitProtocol](CAPLfunctionAfdxInitProtocol.md)
- [AfdxInitSchedule](CAPLfunctionAfdxInitSchedule.md)
- [AfdxIsPacketValid](CAPLfunctionAfdxIsPacketValid.md)
- [AfdxIsReceiveCallbackRegistered](CAPLfunctionAfdxIsReceiveCallbackRegistered.md)
- [AfdxOutputPacket](CAPLfunctionAfdxOutputPacket.md)
- [AfdxOutputPacketRaw](CAPLfunctionAfdxOutputPacketRaw.md)
- [AfdxOutputPacketWithSignals](CAPLfunctionAfdxOutputPacketWithSignals.md)
- [AfdxRegisterReceiveCallback](CAPLfunctionAfdxRegisterReceiveCallback.md)
- [AfdxReleasePacket](CAPLfunctionAfdxReleasePacket.md)
- [AfdxRemoveToken](CAPLfunctionAfdxRemoveToken.md)
- [AfdxResizeToken](CAPLfunctionAfdxResizeToken.md)
- [AfdxSetErrorHandler](CAPLfunctionAfdxSetErrorHandler.md)
- [AfdxSetSignalBool](CAPLfunctionAfdxSetSignalBool.md)
- [AfdxSetSignalInt](CAPLfunctionAfdxSetSignalInt.md)
- [AfdxSetSignalInt64](CAPLfunctionAfdxSetSignalInt64.md)
- [AfdxSetSignalOpaque](CAPLfunctionAfdxSetSignalOpaque.md)
- [AfdxSetSignalReal](CAPLfunctionAfdxSetSignalReal.md)
- [AfdxSetSignalStatus](CAPLfunctionAfdxSetSignalStatus.md)
- [AfdxSetSignalString](CAPLfunctionAfdxSetSignalString.md)
- [AfdxSetTokenData](CAPLfunctionAfdxSetTokenData.md)
- [AfdxSetTokenInt](CAPLfunctionAfdxSetTokenInt.md)
- [AfdxSetTokenInt64](CAPLfunctionAfdxSetTokenInt64.md)
- [AfdxSetTokenReal](CAPLfunctionAfdxSetTokenReal.md)
- [AfdxSetTokenString](CAPLfunctionAfdxSetTokenString.md)
- [AfdxSetVerbosity](CAPLfunctionAfdxSetVerbosity.md)
- [Declaration of AFDX Frames](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md)
- [Declaration of AFDX Messages](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXmessage.md)
- [on a664Frame](../EventProcedures/CAPLfunctionAFDXOnA664Frame.md)
- [on a664Message](../EventProcedures/CAPLfunctionAFDXOnA664Message.md)
- [output (AFDX)](CAPLfunctionAfdxOutput.md)
- [Use The Right Operating Mode (AFDX)](../../../CANoeCANalyzer/AFDX/procedures/afdxUseOperatingModes.md)
