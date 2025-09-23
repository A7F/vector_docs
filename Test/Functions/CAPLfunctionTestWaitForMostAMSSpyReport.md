# TestWaitForMostAMSSpyReport

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostAMSSpyReport(int aFBlockId, int aInstanceId, int aFunctionId, unsigned long aTimeout);`
- `long TestWaitForMostAMSSpyReport(char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostAMSSpyReport(char[] aSymbolicMessage, unsigned long aTimeout);`

## Description

Waits for the occurrence of the spy response message (report, op-type > 8) of the specified MOST AMS message.

This may deal with transmission of individual frames (TelID=0) or segmented transmissions. In the case of segmented transmission, the last control message of a correct transmission resolves the wait conditions.

If the message does not arrive by the time the aTimeout expires, the wait condition is still resolved.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring; test module waits infinitely long)
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

[Links: TestWaitForMostSpyReport](CAPLfunctionTestWaitForMostSpyReport.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [TestJoinMostAMSSpyReportEvent](CAPLfunctionTestJoinMostAMSSpyReportEvent.md) • [TestWaitForMostAMSSpyMessage](CAPLfunctionTestWaitForMostAMSSpyMessage.md) • [TestGetWaitEventMostAMSMsgData](CAPLfunctionTestGetWaitEventMostAmsMsgData.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md) • [Input assistance](../../MOST/CAPLfunctionsMOSTInputAssistant.md)
