# AfdxGetLastErrorText

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxGetLastErrorText

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetLastErrorText( dword bufSize, char[] buffer );
```

## Description

Gets the [error code](../CAPLfunctionsAFDXErrorCodes.md) description of the last called Afdx... function.

## Parameters

- **bufSize**: Size of buffer in which the description text is copied.
- **buffer**: Buffer in which the description text is copied.

## Return Values

Number of copied bytes.

## Example

```c
char error[100];
long value;
long packetHandle;

value = AfdxGetTokenInt( packetHandle, "eth", "type" );
if (AfdxGetLastError() == 0)
{
  write("Ethernet Type is 0x%x", value );
}
else
{
  AfdxGetLastErrorText( elCount(error), error );
  write("Error: %s", error );
}
```

## See Also

- [OnAfdxError](../EventProcedures/CAPLfunctionOnAfdxError.md#aanchor8275)
- [OnAfdxPacket](../EventProcedures/CAPLfunctionOnAfdxPacket.md#aanchor29844)
- [A664CloseProxyPort](CAPLfunctionA664CloseProxyPort.md#aanchor6697)
- [A664GetFunctionalStatus](CAPLfunctionA664GetFunctionalStatus.md#aanchor28045)
- [A664InitICMP](CAPLfunctionA664InitICMP.md#aanchor25473)
- [A664InitMessage](CAPLfunctionA664InitMessage.md#aanchor29099)
- [A664InitPayload](CAPLfunctionA664InitPayload.md#aanchor26506)
- [A664InitProxyPort](CAPLfunctionA664InitProxyPort.md#aanchor29069)
- [A664isICMP](CAPLfunctionA664isICMP.md#aanchor21484)
- [A664MsgConfig](CAPLfunctionA664MsgConfig.md#aanchor3382)
- [A664ResizeMessage](CAPLfunctionA664ResizeMessage.md#aanchor5309)
- [A664SetChecksum](CAPLfunctionA664SetChecksum.md#aanchor16745)
- [A664SetFunctionalStatus](CAPLfunctionA664SetFunctionalStatus.md#aanchor3096)
- [A664SetStringSignal](CAPLfunctionA664SetStringSignal.md#aanchor13788)
- [A664TriggerFrame](CAPLfunctionA664TriggerFrame.md#aanchor15139)
- [A664VLConfig](CAPLfunctionA664VLConfig.md#aanchor21681)
- [AFDX CAPL Functions](../CAPLfunctionsAFDXOverview.md#aanchor29248)
- [AFDX Copy-Operator](CAPLfunctionAfdxCopyOperator.md#aanchor29395)
- [AFDX Error Codes](../CAPLfunctionsAFDXErrorCodes.md#aanchor28140)
- [AfdxCompletePacket](CAPLfunctionAfdxCompletePacket.md#aanchor25785)
- [AfdxDeregisterReceiveCallback](CAPLfunctionAfdxDeregisterReceiveCallback.md#aanchor4820)
- [AfdxGetDBAttrAsString](CAPLfunctionAfdxGetDBAttrAsString.md#aanchor28725)
- [AfdxGetDBAttrValue](CAPLfunctionAfdxGetDBAttrValue.md#aanchor14097)
- [AfdxGetDBMessageName](CAPLfunctionAfdxGetDBMessageName.md#aanchor17315)
- [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md#aanchor32077)
- [AfdxGetLastErrorText](#aanchor532)
- [AfdxGetMessageId](CAPLfunctionAfdxGetMessageId.md#aanchor8797)
- [AfdxGetMessageName](CAPLfunctionAfdxGetMessageName.md#aanchor19675)
- [AfdxGetPacketData](CAPLfunctionAfdxGetPacketData.md#aanchor5325)
- [AfdxGetSignalBool](CAPLfunctionAfdxGetSignalBool.md#aanchor30638)
- [AfdxGetSignalInt](CAPLfunctionAfdxGetSignalInt.md#aanchor14911)
- [AfdxGetSignalInt64](CAPLfunctionAfdxGetSignalInt64.md#aanchor22551)
- [AfdxGetSignalOpaque](CAPLfunctionAfdxGetSignalOpaque.md#aanchor16613)
- [AfdxGetSignalReal](CAPLfunctionAfdxGetSignalReal.md#aanchor15470)
- [AfdxGetSignalStatus](CAPLfunctionAfdxGetSignalStatus.md#aanchor25758)
- [AfdxGetSignalString](CAPLfunctionAfdxGetSignalString.md#aanchor6409)
- [AfdxGetTokenData](CAPLfunctionAfdxGetTokenData.md#aanchor21555)
- [AfdxGetTokenInt](CAPLfunctionAfdxGetTokenInt.md#aanchor23615)
- [AfdxGetTokenInt64](CAPLfunctionAfdxGetTokenInt64.md#aanchor23805)
- [AfdxGetTokenLengthBit](CAPLfunctionAfdxGetTokenLengthBit.md#aanchor10038)
- [AfdxGetTokenReal](CAPLfunctionAfdxGetTokenReal.md#aanchor15217)
- [AfdxGetTokenString](CAPLfunctionAfdxGetTokenString.md#aanchor24407)
- [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md#aanchor15578)
- [AfdxInitProtocol](CAPLfunctionAfdxInitProtocol.md#aanchor21919)
- [AfdxInitSchedule](CAPLfunctionAfdxInitSchedule.md#aanchor23018)
- [AfdxIsPacketValid](CAPLfunctionAfdxIsPacketValid.md#aanchor8971)
- [AfdxIsReceiveCallbackRegistered](CAPLfunctionAfdxIsReceiveCallbackRegistered.md#aanchor2978)
- [AfdxOutputPacket](CAPLfunctionAfdxOutputPacket.md#aanchor20349)
- [AfdxOutputPacketRaw](CAPLfunctionAfdxOutputPacketRaw.md#aanchor26500)
- [AfdxOutputPacketWithSignals](CAPLfunctionAfdxOutputPacketWithSignals.md#aanchor31251)
- [AfdxRegisterReceiveCallback](CAPLfunctionAfdxRegisterReceiveCallback.md#aanchor27846)
- [AfdxReleasePacket](CAPLfunctionAfdxReleasePacket.md#aanchor6926)
- [AfdxRemoveToken](CAPLfunctionAfdxRemoveToken.md#aanchor13847)
- [AfdxResizeToken](CAPLfunctionAfdxResizeToken.md#aanchor2529)
- [AfdxSetErrorHandler](CAPLfunctionAfdxSetErrorHandler.md#aanchor4538)
- [AfdxSetSignalBool](CAPLfunctionAfdxSetSignalBool.md#aanchor7641)
- [AfdxSetSignalInt](CAPLfunctionAfdxSetSignalInt.md#aanchor7562)
- [AfdxSetSignalInt64](CAPLfunctionAfdxSetSignalInt64.md#aanchor2043)
- [AfdxSetSignalOpaque](CAPLfunctionAfdxSetSignalOpaque.md#aanchor10575)
- [AfdxSetSignalReal](CAPLfunctionAfdxSetSignalReal.md#aanchor7454)
- [AfdxSetSignalStatus](CAPLfunctionAfdxSetSignalStatus.md#aanchor6107)
- [AfdxSetSignalString](CAPLfunctionAfdxSetSignalString.md#aanchor29371)
- [AfdxSetTokenData](CAPLfunctionAfdxSetTokenData.md#aanchor28262)
- [AfdxSetTokenInt](CAPLfunctionAfdxSetTokenInt.md#aanchor20246)
- [AfdxSetTokenInt64](CAPLfunctionAfdxSetTokenInt64.md#aanchor12574)
- [AfdxSetTokenReal](CAPLfunctionAfdxSetTokenReal.md#aanchor31145)
- [AfdxSetTokenString](CAPLfunctionAfdxSetTokenString.md#aanchor7195)
- [AfdxSetVerbosity](CAPLfunctionAfdxSetVerbosity.md#aanchor4413)
- [Declaration of AFDX Frames](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.md#aanchor9706)
- [Declaration of AFDX Messages](../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXmessage.md#aanchor27421)
- [on a664Frame](../EventProcedures/CAPLfunctionAFDXOnA664Frame.md#aanchor12162)
- [on a664Message](../EventProcedures/CAPLfunctionAFDXOnA664Message.md#aanchor17424)
- [output (AFDX)](CAPLfunctionAfdxOutput.md#aanchor9808)
- [Use The Right Operating Mode (AFDX)](../../../CANoeCANalyzer/AFDX/procedures/afdxUseOperatingModes.md#aanchor17028)
