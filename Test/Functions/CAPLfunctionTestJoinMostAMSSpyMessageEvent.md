[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinMostAMSSpyMessageEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMostAMSSpyMessageEvent

# TestJoinMostAMSSpyMessageEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `TestJoinMostAMSSpyMessageEvent(dbMsg aDBMsg, int aInstanceId)`
- `TestJoinMostAMSSpyMessageEvent(int aFBlockId, int aInstanceId)`
- `TestJoinMostAMSSpyMessageEvent(int aFBlockId, int aInstanceId, int aFunctionId)`
- `TestJoinMostAMSSpyMessageEvent(int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `TestJoinMostAMSSpyMessageEvent(int aSourceAddress, int aDestinationAddress, int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `TestJoinMostAMSSpyMessageEvent(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId)`
- `TestJoinMostAMSSpyMessageEvent(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage)`
- `TestJoinMostAMSSpyMessageEvent(char[] aSymbolicMessage, int aInstanceId)`
- `TestJoinMostAMSSpyMessageEvent(char[] aSymbolicMessage)`

## Description

Completes the current set of "joined events" with the transmitted event, a MOST AMS Spymessage. This may deal with individual frames transmissions (TelID=0) or segmented transmissions. In the case of segmented transmissions, the last control message of a correct transmission triggers the wait condition.

This function does not wait.

The wait point can be subsequently attached with [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) and [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md).

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDBMsg**: MOST function catalog MOST message (e.g. AudioDiskPlayer.TrackPosition.Status) or message name from CANdb database (e.g. ADP_TrackPosition_Status).
- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aFBlockId**: Numeric value of BlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aOpType**: Numeric value of OpTypes
- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - FBlock.InstanceId.Function.OpType(Parameterliste)
  - FBlock.InstanceId.Function.OpType
  - FBlock.Function.OpType(Parameterliste)
  - FBlock.Function
  - FBlock

(see also [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md))

**Note**: For parameters **aSourceAddress**, **aDestinationAddress**, **aFBlockId**, **aInstanceId**, **aFunctionId** and **aOpType** the following applies: If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

## Return Values

- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed
- **-3**: Join error
- **-1**: General error e.g. the functionality is not available
- **> 0**: Number of joined events

## Example

—

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestJoinMostAMSMessageEvent](CAPLfunctionTestJoinMostAMSMessageEvent.md) • [TestJoinMostAMSSpyReportEvent](CAPLfunctionTestJoinMostAMSSpyReportEvent.md) • [TestJoinMostSpyMessageEvent](CAPLfunctionTestJoinMostSpyMessageEvent.md) • [TestWaitForMostAMSSpyMessage](CAPLfunctionTestWaitForMostAMSSpyMessage.md) • [TestGetWaitEventMostAMSMsgData](CAPLfunctionTestGetWaitEventMostAMSMsgData.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
