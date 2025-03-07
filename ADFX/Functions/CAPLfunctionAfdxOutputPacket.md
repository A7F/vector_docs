[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxOutputPacket.md)

**CAPL Functions** » **AFDX** » **AfdxOutputPacket**

# AfdxOutputPacket

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxOutputPacket( long packet ); // form 1
long AfdxOutputPacket( long packet, long txMode, long frag, long vl, long seqNo, long rma ); // form 2
```

## Description

The specified AFDX message is transmitted with this function call. Note that the user has complete control of all the transmission scenarios. If the message is defined in an [AFDX database](../../../CANoeCANalyzer/AFDX/procedures/afdxGenerateDbc.md) the corresponding message attributes (e.g. timing, redundancy) are used for the transmission. Your CANoe DE product internally uses an AFDX software stack for the message handling.

In the following cases the message needs to be defined in a DBC file and the file needs to be assigned to the actual configuration:

- Form 1 is used
- Form 2 is used with at least one of the parameters set to the listed value:
  - txMode = 0 (CyclicOff), 1 (CyclicOn)
  - frag = 1 (DoIPFragmentation)
  - vl = 1 (DoAFDXVLScheduling)
  - rma = 0 (DBRelated)

## Parameters

- **packet**: Handle of the message to send that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).

- **txMode**: Set message’s transmission behavior:
  - 0: (CyclicOff) An active cyclic transmission is switched off. The corresponding message is transmitted at least once after this call.
  - 1: (CyclicOn) The message is transmitted cyclically and the cycle time is defined via the attribute [AfdxMsgTxRate](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportMessageAttributes.md) in the assigned DBC file.
  - 2: (SingleShot) The message is transmitted once.

- **frag**: Activate or deactivate IP fragmentation:
  - 0: (NoIPFragmentation) The message is transmitted without fragmentation.
  - 1: (DoIPFragmentation) This parameter value activates the IP fragmentation for a message based on the attributes in the DBC file. The fragment’s size corresponds to the value of the attribute AfdxVLmaxFrame.

- **vl**: Activate/deactivate software controlled VL scheduling:
  - 0: (NoAFDXVLScheduling) The corresponding virtual link of this message is not controlled by the AFDX software stack.
  - 1: (DoAFDXVLScheduling) The corresponding virtual link of this message is controlled by the AFDX software stack.

- **seqNo**: Activate/deactivate automatic sequence number handling:
  - 0: (NoAFDXSeqNoManagement) The actual sequence number from message’s payload is used.
  - 1: (DoAFDXSeqNoManagement) The sequence number is automatically updated for the message.

- **rma**: Activate a specific redundancy handling mode.

  | Value | Short Name  | Description                                               | Interface_ID updated? | Message duplicated? |
  |-------|-------------|-----------------------------------------------------------|-----------------------|---------------------|
  | 0     | DBRelated   | The line assignment for the message is derived from the assigned DBC file | X                     | X                   |
  | 1     | ForceA      | The message is transmitted on the specified line.         | X                     | —                   |
  | 2     | ForceB      | The message is transmitted on the specified line.         | X                     | —                   |
  | 3     | ForceAB     | The message is transmitted on both lines.                 | X                     | X                   |
  | 4     | ForceAonB   | The message is transmitted on the other line. The assignment is inverted. | X                     | —                   |
  | 5     | ForceBonA   | The message is transmitted on the other line. The assignment is inverted. | X                     | —                   |
  | 6     | ForceABonBA | The message is transmitted on both lines and the line assignment is inverted. | X                     | X                   |
  | 7     | ForceLineA  | The message is transmitted on the specified line.         | —                     | —                   |
  | 8     | ForceLineB  | The message is transmitted on the specified line.         | —                     | —                   |
  | 9     | ForceLineAB | The message is transmitted on both lines.                 | —                     | X                   |
  | 10    | MACIFRelated| The line assignment is derived from the given MAC source address. | —                     | X                   |

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

See example of [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md)

**See Also**

- [OnAfdxError](../EventProcedures/CAPLfunctionOnAfdxError.md#aanchor8275)
- [OnAfdxPacket](../EventProcedures/CAPLfunctionOnAfdxPacket.md#aanchor29844)
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
- [AfdxInitSchedule](CAPLfunctionAfdxInitSchedule.md#aanchor23018)
- [AfdxIsPacketValid](CAPLfunctionAfdxIsPacketValid.md#aanchor8971)
- [AfdxIsReceiveCallbackRegistered](CAPLfunctionAfdxIsReceiveCallbackRegistered.md#aanchor2978)
- [AfdxOutputPacket](#aanchor20349)
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