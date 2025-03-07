[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxInitSchedule.md)

**CAPL Functions** » **AFDX** » **AfdxInitSchedule**

# AfdxInitSchedule

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxInitSchedule( long packet );
```

## Description

Initializes the [scheduled transmission](../../../CANoeCANalyzer/AFDX/afdxBasics/afdxScheduling.md) of the specified message during the start phase of the measurement.

The behavior of the function call differs for different [measurement phases](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

- **on preStart**: The schedule is temporarily buffered till the environment is fully initialized. Afterwards the scheduler controlled transmission starts automatically. Only one schedule per [message ID](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportIntro.md) can be instantiated.
- **on start/during measurement**: The packet is scheduled immediately. This corresponds to a call of [AfdxOutputPaket(packet, CyclicOn, DoIPFragmentation, DoAFDXVLScheduling, DoAFDXSeqNoManagement, DBRelated)](CAPLfunctionAfdxOutputPacket.md).

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).

## Return Values

- **0**: 
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

```plaintext
on preStart
{
  long packet;
  char errTxt[256];

  packet = AfdxInitPacket(0, "TESTMSG_ALLTYPES", 0 );
  if (packet == 0)
  {
    AfdxGetLastErrorText(elCount(errTxt), errTxt);
    writeEx( -3, 0, "<%NODE_NAME%> AfdxInitPacket failed due to:%s", errTxt );
  }

  if (AfdxInitSchedule(packet) != 0)
  {
    AfdxGetLastErrorText(elCount(errTxt), errTxt);
    writeEx( -3, 0, "<%NODE_NAME%> AfdxInitSchedule failed due to:%s", errTxt );
  }
  AfdxReleasePacket(packet);
}
```

[See Also](javascript:void(0);)
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
- [AfdxGetLastErrorText](CAPLfunctionAfdxGetLastErrorText.md#aanchor532)
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
- [AfdxInitSchedule](#aanchor23018)
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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)