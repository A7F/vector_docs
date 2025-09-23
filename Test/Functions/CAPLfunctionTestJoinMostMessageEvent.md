# TestJoinMostMessageEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestJoinMostMessageEvent (dbMsg aDBMsg, int aInstanceId)`
- `long TestJoinMostMessageEvent (int aFBlockId, int aInstanceId)`
- `long TestJoinMostMessageEvent (int aFBlockId, int aInstanceId, int aFunctionId)`
- `long TestJoinMostMessageEvent (int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `long TestJoinMostMessageEvent (int aSourceAddress, int aDestinationAddress, int aFBlockId, int aInstanceId, int aFunctionId, int aOpType)`
- `long TestJoinMostMessageEvent (int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId)`
- `long TestJoinMostMessageEvent (int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage)`
- `long TestJoinMostMessageEvent (char[] aSymbolicMessage, int aInstanceId)`
- `long TestJoinMostMessageEvent (char[] aSymbolicMessage)`

## Description

Completes the current set of "joined events" with the transmitted event, a MOST message (MOST control message or MOST spy message). This function does not wait.

**Note:** Consider setting the appropriate bus context in a multibus environment before calling the function. Further information on [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDBMsg**: MOST function catalog MOST message or message name from CANdb database.
- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aOpType**: Numeric value of OpTypes
- **aSymbolicMessage**: Symbolic MOST message definition in formats like:
  - `FBlock.InstanceId.Function.OpType(Parameterliste)`
  - `FBlock.InstanceId.Function.OpType`
  - `FBlock.Function.OpType(Parameterliste)`
  - `FBlock.Function`
  - `FBlock`
  (See also [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md))

## Return Values

- **-6**: Parse Error; unresolved symbolic message definition.
- **-3**: Join error
- **-1**: General error e.g. functionality not available
- **> 0**: Number of joined events

## Example

—

[**TestJoinMostSpyMessageEvent**](CAPLfunctionTestJoinMostSpyMessageEvent.md) • [**TestWaitForAllJoinedEvents**](CAPLfunctionTestWaitForAllJoinedEvents.md) • [**TestWaitForAnyJoinedEvent**](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [**TestWaitForMostMessage**](CAPLfunctionTestWaitForMostMessage.md) • [**TestWaitForMostReport**](CAPLfunctionTestWaitForMostReport.md) • [**TestJoinMostReportEvent**](CAPLfunctionTestJoinMostReportEvent.md) • [**TestGetWaitEventMostMsgData**](CAPLfunctionTestGetWaitEventMostMsgData.md)
