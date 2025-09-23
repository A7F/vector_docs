# TestWaitForMostReport

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostReport(int aFBlockId, int aInstanceId, int aFunctionId, dword aTimeout);`
- `long TestWaitForMostReport(char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostReport(char[] aSymbolicMessage, unsigned long aTimeout);`

## Description

Waits for the occurrence of a response message (Report, OpType \> 8) of the specified MOST message (MOST control message or MOST spy message). Should the message not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aTimeout**: Maximum wait time [ms] (Transmission of 0: no timeout controlling)
- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - FBlock.InstanceId.Function
  - FBlock.Function
  - FBlock
  (see also [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md))

## Return Values

- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed
- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostSpyReport](CAPLfunctionTestWaitForMostSpyReport.md) • [TestWaitForMostMessage](CAPLfunctionTestWaitForMostMessage.md) • [TestJoinMostMessageEvent](CAPLfunctionTestJoinMostMessageEvent.md) • [TestJoinMostReportEvent](CAPLfunctionTestJoinMostReportEvent.md) • [TestGetWaitEventMostMsgData](CAPLfunctionTestGetWaitEventMostMsgData.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)
