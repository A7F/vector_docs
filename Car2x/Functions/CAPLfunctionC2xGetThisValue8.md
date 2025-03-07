[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetThisValue8.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetThisValue8

# C2xGetThisValue8

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```plaintext
long C2xGetThisValue8( long offset );
```

## Description

This function reads the data of a received packet.

## Parameters

- **offset**: Byte offset relative to the beginning of a data packet or the payload (see description above).

## Return Values

Read value.

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  byte value8;
  value8 = C2xGetThisValue8( 14 );
  write( "Value %d", value8 );
}
```

[See Also](javascript:void(0);)
```markdown
- OnC2xPacket
- OnC2xTransmitPacket
- C2xAddToken
- C2xAssignNodeToStation
- C2xCompletePacket
- C2xConvertTimeFromMSSinceUTC
- C2xConvertTimeToMSSinceUTC
- C2xCreateStation
- C2xDisableMsg
- C2xEnableMsg
- C2xGetCycleTime
- C2xGetDefaultMacId
- C2xGetITSTimeStamp
- C2xGetLastError
- C2xGetLastErrorText
- C2xGetMessageName
- C2xGetNodeName
- C2xGetStationHandle
- C2xGetStationHandleByStationName
- C2xGetStationName
- C2xGetThisData
- C2xGetThisMotorolaValue16
- C2xGetThisMotorolaValue32
- C2xGetThisMotorolaValue64
- C2xGetThisTimeNS
- C2xGetThisValue16
- C2xGetThisValue32
- C2xGetThisValue64
- C2xGetThisValue8
- C2xGetTokenBitOfBitString
- C2xGetTokenBitString
- C2xGetTokenData
- C2xGetTokenInt
- C2xGetTokenInt64
- C2xGetTokenLengthBit
- C2xGetTokenOidElement
- C2xGetTokenString
- C2xGetTokenSubString
- C2xInitPacket
- C2xInitProtocol
- C2xIsMsgEnabled
- C2xIsNodeStarted
- C2xIsPacketValid
- C2xIsTokenAvailable
- C2xOutputPacket
- C2xProtocolAnalyzerGetRuleList
- C2xReceivePacket
- C2xRegisterCallback
- C2xReleasePacket
- C2xRemoveNodeAssignment
- C2xRemoveToken
- C2xReportProtocolViolation
- C2xResizeToken
- C2xSecCertificateCreate
- C2xSecCertificateGetHandle
- C2xSecCertificateGetHashedId8
- C2xSecCertificateGetName
- C2xSecCertificateGetSignerHandle
- C2xSecCertificateGetSignerHashedId8
- C2xSecCertificateGetStatus
- C2xSecPacketGetSignerHandle
- C2xSecPacketGetSignerHashedId8
- C2xSecPacketGetSignerType
- C2xSecPacketGetStatus
- C2xSecPacketIsSecured
- C2xSecPacketSetSignerHandle
- C2xSecPacketSetSignerType
- C2xSendMsg
- C2xSetCycleTime
- C2xSetSignal
- C2xSetStationSpeed
- C2xSetTokenBitOfBitString
- C2xSetTokenBitString
- C2xSetTokenData
- C2xSetTokenInt
- C2xSetTokenInt64
- C2xSetTokenOidElement
- C2xSetTokenString
- C2xSetVerbosity
- Car2x CAPL Functions
- Car2x Error Codes
- OnProtocolViolation
- OnScenarioStateChanged
- OnStartScenario
- OnStationAttributeTrigger
- OnStationAttributeTriggerAll
- SetStationSpeed
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)