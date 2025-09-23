# TestJoinMostAMSMessageEvent

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `long TestJoinMostAMSMessageEvent(dbMsg aDBMsg, int aInstanceId)`
- `long TestJoinMostAMSMessageEvent(int aFBlockId, int aInstanceId)`
- `long TestJoinMostAMSMessageEvent(int aFBlockId, int aInstanceId, int aFunctionId)`
- `long TestJoinMostAMSMessageEvent(int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `long TestJoinMostAMSMessageEvent(int aSourceAddress, int aDestinationAddress, int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `long TestJoinMostAMSMessageEvent(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId)`
- `long TestJoinMostAMSMessageEvent(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage)`
- `long TestJoinMostAMSMessageEvent(char[] aSymbolicMessage, int aInstanceId)`
- `long TestJoinMostAMSMessageEvent(char[] aSymbolicMessage)`

## Description

Completes the current set of "joined events" with the transmitted event, a MOST AMS message. This function does not wait.

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

[Links to related topics](CAPLfunctionTestJoinMostAMSSpyMessageEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForMostAMSMessage](CAPLfunctionTestWaitForMostAMSMessage.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [TestJoinMostAMSReportEvent](CAPLfunctionTestJoinMostAMSReportEvent.md) • [TestGetWaitEventMostAMSMsgData](CAPLfunctionTestGetWaitEventMostAmsMsgData.md)
