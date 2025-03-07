[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetTokenReal.md)

CAPL Functions » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxGetTokenReal

# AfdxGetTokenReal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
float AfdxGetTokenReal( long packet, char protocolDesignator[], char tokenDesignator[], long offset, long length );
```

## Description

This function returns the specified token's data as a [float](../../../Shared/CAPL/General/DataTypesForFunctionParameters.md) value.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md) or from within a callback.
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "udp".
- **tokenDesignator**: Name of the token, e.g. "data".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **length**: The values 4 (32-bit float value) and 8 (64-bit float value) are allowed here. This is the length of the value to be returned from the token's data area.

## Return Values

Integer value gathered from the token's data. With [AfdxGetLastError](CAPLfunctionAfdxGetLastError.md) you have to check if the function has been processed successfully.

## Example

```plaintext
void OnAfdxPacket(long channel, long dir, long flags, long bag, long packet )
{
  double temperature;
  char error[100];

  // get temperature value from payload position 8 as a float (4byte length)
  temperature = AfdxGetTokenReal( packet, "udp", "data", 8, 4 );

  if (AfdxGetLastError() == 0)
  {
    // do something with temperature
  }
  else
  {
    AfdxGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```

[See Also](javascript:void(0);)
```markdown
- <OnAfdxError> | ../EventProcedures/CAPLfunctionOnAfdxError.htm#aanchor8275
- <OnAfdxPacket> | ../EventProcedures/CAPLfunctionOnAfdxPacket.htm#aanchor29844
- A664CloseProxyPort | CAPLfunctionA664CloseProxyPort.htm#aanchor6697
- A664GetFunctionalStatus | CAPLfunctionA664GetFunctionalStatus.htm#aanchor28045
- A664InitICMP | CAPLfunctionA664InitICMP.htm#aanchor25473
- A664InitMessage | CAPLfunctionA664InitMessage.htm#aanchor29099
- A664InitPayload | CAPLfunctionA664InitPayload.htm#aanchor26506
- A664InitProxyPort | CAPLfunctionA664InitProxyPort.htm#aanchor29069
- A664isICMP | CAPLfunctionA664isICMP.htm#aanchor21484
- A664MsgConfig | CAPLfunctionA664MsgConfig.htm#aanchor3382
- A664ResizeMessage | CAPLfunctionA664ResizeMessage.htm#aanchor5309
- A664SetChecksum | CAPLfunctionA664SetChecksum.htm#aanchor16745
- A664SetFunctionalStatus | CAPLfunctionA664SetFunctionalStatus.htm#aanchor3096
- A664SetStringSignal | CAPLfunctionA664SetStringSignal.htm#aanchor13788
- A664TriggerFrame | CAPLfunctionA664TriggerFrame.htm#aanchor15139
- A664VLConfig | CAPLfunctionA664VLConfig.htm#aanchor21681
- AFDX CAPL Functions | ../CAPLfunctionsAFDXOverview.htm#aanchor29248
- AFDX Copy-Operator | CAPLfunctionAfdxCopyOperator.htm#aanchor29395
- AFDX Error Codes | ../CAPLfunctionsAFDXErrorCodes.htm#aanchor28140
- AfdxCompletePacket | CAPLfunctionAfdxCompletePacket.htm#aanchor25785
- AfdxDeregisterReceiveCallback | CAPLfunctionAfdxDeregisterReceiveCallback.htm#aanchor4820
- AfdxGetDBAttrAsString | CAPLfunctionAfdxGetDBAttrAsString.htm#aanchor28725
- AfdxGetDBAttrValue | CAPLfunctionAfdxGetDBAttrValue.htm#aanchor14097
- AfdxGetDBMessageName | CAPLfunctionAfdxGetDBMessageName.htm#aanchor17315
- AfdxGetLastError | CAPLfunctionAfdxGetLastError.htm#aanchor32077
- AfdxGetLastErrorText | CAPLfunctionAfdxGetLastErrorText.htm#aanchor532
- AfdxGetMessageId | CAPLfunctionAfdxGetMessageId.htm#aanchor8797
- AfdxGetMessageName | CAPLfunctionAfdxGetMessageName.htm#aanchor19675
- AfdxGetPacketData | CAPLfunctionAfdxGetPacketData.htm#aanchor5325
- AfdxGetSignalBool | CAPLfunctionAfdxGetSignalBool.htm#aanchor30638
- AfdxGetSignalInt | CAPLfunctionAfdxGetSignalInt.htm#aanchor14911
- AfdxGetSignalInt64 | CAPLfunctionAfdxGetSignalInt64.htm#aanchor22551
- AfdxGetSignalOpaque | CAPLfunctionAfdxGetSignalOpaque.htm#aanchor16613
- AfdxGetSignalReal | CAPLfunctionAfdxGetSignalReal.htm#aanchor15470
- AfdxGetSignalStatus | CAPLfunctionAfdxGetSignalStatus.htm#aanchor25758
- AfdxGetSignalString | CAPLfunctionAfdxGetSignalString.htm#aanchor6409
- AfdxGetTokenData | CAPLfunctionAfdxGetTokenData.htm#aanchor21555
- AfdxGetTokenInt | CAPLfunctionAfdxGetTokenInt.htm#aanchor23615
- AfdxGetTokenInt64 | CAPLfunctionAfdxGetTokenInt64.htm#aanchor23805
- AfdxGetTokenLengthBit | CAPLfunctionAfdxGetTokenLengthBit.htm#aanchor10038
- AfdxGetTokenReal | #aanchor15217
- AfdxGetTokenString | CAPLfunctionAfdxGetTokenString.htm#aanchor24407
- AfdxInitPacket | CAPLfunctionAfdxInitPacket.htm#aanchor15578
- AfdxInitProtocol | CAPLfunctionAfdxInitProtocol.htm#aanchor21919
- AfdxInitSchedule | CAPLfunctionAfdxInitSchedule.htm#aanchor23018
- AfdxIsPacketValid | CAPLfunctionAfdxIsPacketValid.htm#aanchor8971
- AfdxIsReceiveCallbackRegistered | CAPLfunctionAfdxIsReceiveCallbackRegistered.htm#aanchor2978
- AfdxOutputPacket | CAPLfunctionAfdxOutputPacket.htm#aanchor20349
- AfdxOutputPacketRaw | CAPLfunctionAfdxOutputPacketRaw.htm#aanchor26500
- AfdxOutputPacketWithSignals | CAPLfunctionAfdxOutputPacketWithSignals.htm#aanchor31251
- AfdxRegisterReceiveCallback | CAPLfunctionAfdxRegisterReceiveCallback.htm#aanchor27846
- AfdxReleasePacket | CAPLfunctionAfdxReleasePacket.htm#aanchor6926
- AfdxRemoveToken | CAPLfunctionAfdxRemoveToken.htm#aanchor13847
- AfdxResizeToken | CAPLfunctionAfdxResizeToken.htm#aanchor2529
- AfdxSetErrorHandler | CAPLfunctionAfdxSetErrorHandler.htm#aanchor4538
- AfdxSetSignalBool | CAPLfunctionAfdxSetSignalBool.htm#aanchor7641
- AfdxSetSignalInt | CAPLfunctionAfdxSetSignalInt.htm#aanchor7562
- AfdxSetSignalInt64 | CAPLfunctionAfdxSetSignalInt64.htm#aanchor2043
- AfdxSetSignalOpaque | CAPLfunctionAfdxSetSignalOpaque.htm#aanchor10575
- AfdxSetSignalReal | CAPLfunctionAfdxSetSignalReal.htm#aanchor7454
- AfdxSetSignalStatus | CAPLfunctionAfdxSetSignalStatus.htm#aanchor6107
- AfdxSetSignalString | CAPLfunctionAfdxSetSignalString.htm#aanchor29371
- AfdxSetTokenData | CAPLfunctionAfdxSetTokenData.htm#aanchor28262
- AfdxSetTokenInt | CAPLfunctionAfdxSetTokenInt.htm#aanchor20246
- AfdxSetTokenInt64 | CAPLfunctionAfdxSetTokenInt64.htm#aanchor12574
- AfdxSetTokenReal | CAPLfunctionAfdxSetTokenReal.htm#aanchor31145
- AfdxSetTokenString | CAPLfunctionAfdxSetTokenString.htm#aanchor7195
- AfdxSetVerbosity | CAPLfunctionAfdxSetVerbosity.htm#aanchor4413
- Declaration of AFDX Frames | ../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXframe.htm#aanchor9706
- Declaration of AFDX Messages | ../../../CANoeCANalyzer/AFDX/capl/afdxDefineAFDXmessage.htm#aanchor27421
- on a664Frame | ../EventProcedures/CAPLfunctionAFDXOnA664Frame.htm#aanchor12162
- on a664Message | ../EventProcedures/CAPLfunctionAFDXOnA664Message.htm#aanchor17424
- output (AFDX) | CAPLfunctionAfdxOutput.htm#aanchor9808
- Use The Right Operating Mode (AFDX) | ../../../CANoeCANalyzer/AFDX/procedures/afdxUseOperatingModes.htm#aanchor17028
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)