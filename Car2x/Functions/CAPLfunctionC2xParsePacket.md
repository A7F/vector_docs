# C2xParsePacket

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xParsePacket.md)

**CAPL Functions** » **Car2x** » **C2xParsePacket**

## Function Syntax

```plaintext
long C2xParsePacket(long packet)
```

## Description

Reinterprets the packet after externally defined binary payload data has been assigned to the packet.

When parts of the packet are already available as byte array from external sources, for example gateways or traffic intersection geometry design tools (for MAP packet), these binary byte arrays can be applied to the packet by using `C2xSetTokenData` function. Here mentioned are byte arrays representing the whole header payload parts like wsmp_t/data, dsmp/data or btp/data and not the data of specific concrete payload tokens.

By calling `C2xParsePacket` the packet will be reinterpreted, so directly after the call the values of each token existed in external data are accessible (see the example).

This function fails when the external data applied to the packet cannot be successfully interpreted by using database message definitions.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md) or was obtained via callback function parameter.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
void ApplyASN1DataCN(long packet, byte asn1data[], long asn1length)
{
  C2xResizeToken(packet, "dsmp", "data", asn1length*8);
  C2xSetTokenData(packet, "dsmp", "data", asn1length, asn1data);
  C2xParsePacket(packet);
}

void ApplyASN1DataEU(long packet, byte asn1data[], long asn1length)
{
  C2xResizeToken(packet, "btp", "data", asn1length*8);
  C2xSetTokenData(packet, "btp", "data", asn1length, asn1data);
  C2xParsePacket(packet);
}

void ApplyASN1DataUS(long packet, byte asn1data[], long asn1length)
{
  C2xResizeToken(packet, "wsmp_t", "data", asn1length*8);
  C2xSetTokenData(packet, "wsmp_t", "data", asn1length, asn1data);
  C2xParsePacket(packet);
}

variables
{
  long hBSM; // Handle to the new BasicSatetyMessage
  byte asn1Payload[3000]; // Holds external data
  long asn1Payload_length;
}

// Emulate the external ASN.1 data source ("asn1Payload" byte array) by copying the data from an existing packet
long OnPreTxBasicSafetyMessage(LONG packet)
{
  C2xSetTokenInt(packet, "BasicSafetyMessage", "value.basicSafetyMessage.coreData.msgCnt", 2);
  C2xCompletePacket(packet);
  // Get external data, "asn1Payload" can be also set
  // via gateway data, loaded from file, etc.
  asn1Payload_length = C2xGetTokenData(packet, "wsmp_t", "data", elcount(asn1Payload), asn1Payload);
  hBSM = C2xInitPacket("wsmp_t","");
  // Paste external data on a new US BasicSafety message
  ApplyASN1Data(hBSM, asn1Payload,asn1Payload_length);
  write("msgCnt = %d", C2xGetTokenInt(hBSM, "BasicSafetyMessage", "value.basicSafetyMessage.coreData.msgCnt"));
  C2xOutputPacket(hBSM);
  return 0;
}
```

## See Also

- [C2xAddToken](CAPLfunctionC2xAddToken.md)
- [C2xAssignNodeToStation](CAPLfunctionC2xAssignNodeToStation.md)
- [C2xCompletePacket](CAPLfunctionC2xCompletePacket.md)
- [C2xConvertTimeFromMSSinceUTC](CAPLfunctionC2xConvertTimeFromMSSinceUTC.md)
- [C2xConvertTimeToMSSinceUTC](CAPLfunctionC2xConvertTimeToMSSinceUTC.md)
- [C2xCreateStation](CAPLfunctionC2xCreateStation.md)
- [C2xDisableMsg](CAPLfunctionC2xDisableMsg.md)
- [C2xEnableMsg](CAPLfunctionC2xEnableMsg.md)
- [C2xGetCycleTime](CAPLfunctionC2xGetCycleTime.md)
- [C2xGetDefaultMacId](CAPLfunctionC2xGetDefaultMacId.md)
- [C2xGetITSTimeStamp](CAPLfunctionC2xGetITSTimeStamp.md)
- [C2xGetLastError](CAPLfunctionC2xGetLastError.md)
- [C2xGetLastErrorText](CAPLfunctionC2xGetLastErrorText.md)
- [C2xGetMessageName](CAPLfunctionC2xGetMessageName.md)
- [C2xGetNodeName](CAPLfunctionC2xGetNodeName.md)
- [C2xGetStationHandle](CAPLfunctionC2xGetStationHandle.md)
- [C2xGetStationHandleByStationName](CAPLfunctionC2xGetStationHandleByStationName.md)
- [C2xGetStationName](CAPLfunctionC2xGetStationName.md)
- [C2xGetThisData](CAPLfunctionC2xGetThisData.md)
- [C2xGetThisMotorolaValue16](CAPLfunctionC2xGetThisMotorolaValue16.md)
- [C2xGetThisMotorolaValue32](CAPLfunctionC2xGetThisMotorolaValue32.md)
- [C2xGetThisMotorolaValue64](CAPLfunctionC2xGetThisMotorolaValue64.md)
- [C2xGetThisTimeNS](CAPLfunctionC2xGetThisTimeNS.md)
- [C2xGetThisValue16](CAPLfunctionC2xGetThisValue16.md)
- [C2xGetThisValue32](CAPLfunctionC2xGetThisValue32.md)
- [C2xGetThisValue64](CAPLfunctionC2xGetThisValue64.md)
- [C2xGetThisValue8](CAPLfunctionC2xGetThisValue8.md)
- [C2xGetTokenBitOfBitString](CAPLfunctionC2xGetTokenBitOfBitString.md)
- [C2xGetTokenBitString](CAPLfunctionC2xGetTokenBitString.md)
- [C2xGetTokenData](CAPLfunctionC2xGetTokenData.md)
- [C2xGetTokenInt](CAPLfunctionC2xGetTokenInt.md)
- [C2xGetTokenInt64](CAPLfunctionC2xGetTokenInt64.md)
- [C2xGetTokenLengthBit](CAPLfunctionC2xGetTokenLengthBit.md)
- [C2xGetTokenOidElement](CAPLfunctionC2xGetTokenOidElement.md)
- [C2xGetTokenString](CAPLfunctionC2xGetTokenString.md)
- [C2xGetTokenSubString](CAPLfunctionC2xGetTokenSubString.md)
- [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- [C2xInitProtocol](CAPLfunctionC2xInitProtocol.md)
- [C2xIsMsgEnabled](CAPLfunctionC2xIsMsgEnabled.md)
- [C2xIsNodeStarted](CAPLfunctionC2xIsNodeStarted.md)
- [C2xIsPacketValid](CAPLfunctionC2xIsPacketValid.md)
- [C2xIsTokenAvailable](CAPLfunctionC2xIsTokenAvailable.md)
- [C2xOutputPacket](CAPLfunctionC2xOutputPacket.md)
- [C2xProtocolAnalyzerGetRuleList](CAPLfunctionC2xProtocolAnalyzerGetRuleList.md)
- [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md)
- [C2xRegisterCallback](CAPLfunctionC2xRegisterCallback.md)
- [C2xReleasePacket](CAPLfunctionC2xReleasePacket.md)
- [C2xRemoveNodeAssignment](CAPLfunctionC2xRemoveNodeAssignment.md)
- [C2xRemoveToken](CAPLfunctionC2xRemoveToken.md)
- [C2xReportProtocolViolation](CAPLfunctionC2xReportProtocolViolation.md)
- [C2xResizeToken](CAPLfunctionC2xResizeToken.md)
- [C2xSecCertificateCreate](CAPLfunctionC2xSecCertificateCreate.md)
- [C2xSecCertificateGetHandle](CAPLfunctionC2xSecCertificateGetHandle.md)
- [C2xSecCertificateGetHashedId8](CAPLfunctionC2xSecCertificateGetHashedId8.md)
- [C2xSecCertificateGetName](CAPLfunctionC2xSecCertificateGetName.md)
- [C2xSecCertificateGetSignerHandle](CAPLfunctionC2xSecCertificateGetSignerHandle.md)
- [C2xSecCertificateGetSignerHashedId8](CAPLfunctionC2xSecCertificateGetSignerHashedId8.md)
- [C2xSecCertificateGetStatus](CAPLfunctionC2xSecCertificateGetStatus.md)
- [C2xSecPacketGetSignerHandle](CAPLfunctionC2xSecPacketGetSignerHandle.md)
- [C2xSecPacketGetSignerHashedId8](CAPLfunctionC2xSecPacketGetSignerHashedId8.md)
- [C2xSecPacketGetSignerType](CAPLfunctionC2xSecPacketGetSignerType.md)
- [C2xSecPacketGetStatus](CAPLfunctionC2xSecPacketGetStatus.md)
- [C2xSecPacketIsSecured](CAPLfunctionC2xSecPacketIsSecured.md)
- [C2xSecPacketSetSignerHandle](CAPLfunctionC2xSecPacketSetSignerHandle.md)
- [C2xSecPacketSetSignerType](CAPLfunctionC2xSecPacketSetSignerType.md)
- [C2xSendMsg](CAPLfunctionC2xSendMsg.md)
- [C2xSetCycleTime](CAPLfunctionC2xSetCycleTime.md)
- [C2xSetSignal](CAPLfunctionC2xSetSignal.md)
- [C2xSetStationSpeed](CAPLfunctionC2xSetStationSpeed.md)
- [C2xSetTokenBitOfBitString](CAPLfunctionC2xSetTokenBitOfBitString.md)
- [C2xSetTokenBitString](CAPLfunctionC2xSetTokenBitString.md)
- [C2xSetTokenData](CAPLfunctionC2xSetTokenData.md)
- [C2xSetTokenInt](CAPLfunctionC2xSetTokenInt.md)
- [C2xSetTokenInt64](CAPLfunctionC2xSetTokenInt64.md)
- [C2xSetTokenOidElement](CAPLfunctionC2xSetTokenOidElement.md)
- [C2xSetTokenString](CAPLfunctionC2xSetTokenString.md)
- [C2xSetVerbosity](CAPLfunctionC2xSetVerbosity.md)
- [Car2x CAPL Functions](../CAPLfunctionsCar2xOverview.md)
- [Car2x Error Codes](../CAPLfunctionsCar2xErrorCodes.md)
- [OnProtocolViolation](../Callbacks/CAPLfunctionC2xOnProtocolViolation.md)
- [OnScenarioStateChanged](../Callbacks/CAPLfunctionC2xOnScenarioStateChanged.md)
- [OnStartScenario](../Callbacks/CAPLfunctionC2xOnStartScenario.md)
- [OnStationAttributeTrigger](../Callbacks/CAPLfunctionC2xOnStationAttributeTrigger.md)
- [OnStationAttributeTriggerAll](../Callbacks/CAPLfunctionC2xOnStationAttributeTriggerAll.md)
- [SetStationSpeed](../../ADAS/Functions/CAPLfunctionSetStationSpeed.md)