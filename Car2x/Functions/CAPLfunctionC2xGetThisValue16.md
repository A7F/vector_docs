# C2xGetThisValue16

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetThisValue16

**Valid for**: CANoe DE

**Note**: This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```plaintext
long C2xGetThisValue16( long offset );
```

## Description

This function reads the data of a received packet in Intel format.

## Parameters

- **offset**: Byte offset relative to the beginning of a data packet or the payload (see description above).

## Return Values

Read value.

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  word value16;
  value16 = C2xGetThisValue16( 14 );
  write( "Value %d", value16 );
}
```

## See Also

- [OnC2xPacket](../Callbacks/CAPLfunctionC2xOnC2xPacket.md#aanchor23975)
- [C2xAddToken](CAPLfunctionC2xAddToken.md#aanchor432)
- [C2xAssignNodeToStation](CAPLfunctionC2xAssignNodeToStation.md#aanchor31711)
- [C2xCompletePacket](CAPLfunctionC2xCompletePacket.md#aanchor17662)
- [C2xConvertTimeFromMSSinceUTC](CAPLfunctionC2xConvertTimeFromMSSinceUTC.md#aanchor11472)
- [C2xConvertTimeToMSSinceUTC](CAPLfunctionC2xConvertTimeToMSSinceUTC.md#aanchor26867)
- [C2xCreateStation](CAPLfunctionC2xCreateStation.md#aanchor5846)
- [C2xDisableMsg](CAPLfunctionC2xDisableMsg.md#aanchor28570)
- [C2xEnableMsg](CAPLfunctionC2xEnableMsg.md#aanchor1395)
- [C2xGetCycleTime](CAPLfunctionC2xGetCycleTime.md#aanchor30852)
- [C2xGetDefaultMacId](CAPLfunctionC2xGetDefaultMacId.md#aanchor31770)
- [C2xGetITSTimeStamp](CAPLfunctionC2xGetITSTimeStamp.md#aanchor24425)
- [C2xGetLastError](CAPLfunctionC2xGetLastError.md#aanchor26849)
- [C2xGetLastErrorText](CAPLfunctionC2xGetLastErrorText.md#aanchor11927)
- [C2xGetMessageName](CAPLfunctionC2xGetMessageName.md#aanchor21385)
- [C2xGetNodeName](CAPLfunctionC2xGetNodeName.md#aanchor21077)
- [C2xGetStationHandle](CAPLfunctionC2xGetStationHandle.md#aanchor13289)
- [C2xGetStationHandleByStationName](CAPLfunctionC2xGetStationHandleByStationName.md#aanchor22716)
- [C2xGetStationName](CAPLfunctionC2xGetStationName.md#aanchor17724)
- [C2xGetThisData](CAPLfunctionC2xGetThisData.md#aanchor31214)
- [C2xGetThisMotorolaValue16](CAPLfunctionC2xGetThisMotorolaValue16.md#aanchor23999)
- [C2xGetThisMotorolaValue32](CAPLfunctionC2xGetThisMotorolaValue32.md#aanchor19990)
- [C2xGetThisMotorolaValue64](CAPLfunctionC2xGetThisMotorolaValue64.md#aanchor28428)
- [C2xGetThisTimeNS](CAPLfunctionC2xGetThisTimeNS.md#aanchor14481)
- [C2xGetThisValue16](#aanchor22593)
- [C2xGetThisValue32](CAPLfunctionC2xGetThisValue32.md#aanchor7857)
- [C2xGetThisValue64](CAPLfunctionC2xGetThisValue64.md#aanchor18307)
- [C2xGetThisValue8](CAPLfunctionC2xGetThisValue8.md#aanchor25439)
- [C2xGetTokenBitOfBitString](CAPLfunctionC2xGetTokenBitOfBitString.md#aanchor13514)
- [C2xGetTokenBitString](CAPLfunctionC2xGetTokenBitString.md#aanchor6435)
- [C2xGetTokenData](CAPLfunctionC2xGetTokenData.md#aanchor9567)
- [C2xGetTokenInt](CAPLfunctionC2xGetTokenInt.md#aanchor5591)
- [C2xGetTokenInt64](CAPLfunctionC2xGetTokenInt64.md#aanchor21630)
- [C2xGetTokenLengthBit](CAPLfunctionC2xGetTokenLengthBit.md#aanchor28400)
- [C2xGetTokenOidElement](CAPLfunctionC2xGetTokenOidElement.md#aanchor21791)
- [C2xGetTokenString](CAPLfunctionC2xGetTokenString.md#aanchor30208)
- [C2xGetTokenSubString](CAPLfunctionC2xGetTokenSubString.md#aanchor31078)
- [C2xInitPacket](CAPLfunctionC2xInitPacket.md#aanchor22422)
- [C2xInitProtocol](CAPLfunctionC2xInitProtocol.md#aanchor11096)
- [C2xIsMsgEnabled](CAPLfunctionC2xIsMsgEnabled.md#aanchor597)
- [C2xIsNodeStarted](CAPLfunctionC2xIsNodeStarted.md#aanchor10424)
- [C2xIsPacketValid](CAPLfunctionC2xIsPacketValid.md#aanchor11613)
- [C2xIsTokenAvailable](CAPLfunctionC2xIsTokenAvailable.md#aanchor30372)
- [C2xOutputPacket](CAPLfunctionC2xOutputPacket.md#aanchor24725)
- [C2xProtocolAnalyzerGetRuleList](CAPLfunctionC2xProtocolAnalyzerGetRuleList.md#aanchor19353)
- [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md#aanchor8450)
- [C2xRegisterCallback](CAPLfunctionC2xRegisterCallback.md#aanchor19511)
- [C2xReleasePacket](CAPLfunctionC2xReleasePacket.md#aanchor12868)
- [C2xRemoveNodeAssignment](CAPLfunctionC2xRemoveNodeAssignment.md#aanchor4504)
- [C2xRemoveToken](CAPLfunctionC2xRemoveToken.md#aanchor25632)
- [C2xReportProtocolViolation](CAPLfunctionC2xReportProtocolViolation.md#aanchor25704)
- [C2xResizeToken](CAPLfunctionC2xResizeToken.md#aanchor26129)
- [C2xSecCertificateCreate](CAPLfunctionC2xSecCertificateCreate.md#aanchor32074)
- [C2xSecCertificateGetHandle](CAPLfunctionC2xSecCertificateGetHandle.md#aanchor20814)
- [C2xSecCertificateGetHashedId8](CAPLfunctionC2xSecCertificateGetHashedId8.md#aanchor27158)
- [C2xSecCertificateGetName](CAPLfunctionC2xSecCertificateGetName.md#aanchor18699)
- [C2xSecCertificateGetSignerHandle](CAPLfunctionC2xSecCertificateGetSignerHandle.md#aanchor21154)
- [C2xSecCertificateGetSignerHashedId8](CAPLfunctionC2xSecCertificateGetSignerHashedId8.md#aanchor29936)
- [C2xSecCertificateGetStatus](CAPLfunctionC2xSecCertificateGetStatus.md#aanchor30775)
- [C2xSecPacketGetSignerHandle](CAPLfunctionC2xSecPacketGetSignerHandle.md#aanchor21036)
- [C2xSecPacketGetSignerHashedId8](CAPLfunctionC2xSecPacketGetSignerHashedId8.md#aanchor19963)
- [C2xSecPacketGetSignerType](CAPLfunctionC2xSecPacketGetSignerType.md#aanchor4292)
- [C2xSecPacketGetStatus](CAPLfunctionC2xSecPacketGetStatus.md#aanchor28304)
- [C2xSecPacketIsSecured](CAPLfunctionC2xSecPacketIsSecured.md#aanchor27826)
- [C2xSecPacketSetSignerHandle](CAPLfunctionC2xSecPacketSetSignerHandle.md#aanchor22383)
- [C2xSecPacketSetSignerType](CAPLfunctionC2xSecPacketSetSignerType.md#aanchor21150)
- [C2xSendMsg](CAPLfunctionC2xSendMsg.md#aanchor30827)
- [C2xSetCycleTime](CAPLfunctionC2xSetCycleTime.md#aanchor28094)
- [C2xSetSignal](CAPLfunctionC2xSetSignal.md#aanchor20968)
- [C2xSetStationSpeed](CAPLfunctionC2xSetStationSpeed.md#aanchor884)
- [C2xSetTokenBitOfBitString](CAPLfunctionC2xSetTokenBitOfBitString.md#aanchor21862)
- [C2xSetTokenBitString](CAPLfunctionC2xSetTokenBitString.md#aanchor22512)
- [C2xSetTokenData](CAPLfunctionC2xSetTokenData.md#aanchor19091)
- [C2xSetTokenInt](CAPLfunctionC2xSetTokenInt.md#aanchor24395)
- [C2xSetTokenInt64](CAPLfunctionC2xSetTokenInt64.md#aanchor5169)
- [C2xSetTokenOidElement](CAPLfunctionC2xSetTokenOidElement.md#aanchor26790)
- [C2xSetTokenString](CAPLfunctionC2xSetTokenString.md#aanchor13042)
- [C2xSetVerbosity](CAPLfunctionC2xSetVerbosity.md#aanchor18792)
- [Car2x CAPL Functions](../CAPLfunctionsCar2xOverview.md#aanchor7431)
- [Car2x Error Codes](../CAPLfunctionsCar2xErrorCodes.md#aanchor16978)
- [OnProtocolViolation](../Callbacks/CAPLfunctionC2xOnProtocolViolation.md#aanchor27621)
- [OnScenarioStateChanged](../Callbacks/CAPLfunctionC2xOnScenarioStateChanged.md#aanchor16247)
- [OnStartScenario](../Callbacks/CAPLfunctionC2xOnStartScenario.md#aanchor4225)
- [OnStationAttributeTrigger](../Callbacks/CAPLfunctionC2xOnStationAttributeTrigger.md#aanchor28915)
- [OnStationAttributeTriggerAll](../Callbacks/CAPLfunctionC2xOnStationAttributeTriggerAll.md#aanchor21716)
- [SetStationSpeed](../../ADAS/Functions/CAPLfunctionSetStationSpeed.md#aanchor28451)
