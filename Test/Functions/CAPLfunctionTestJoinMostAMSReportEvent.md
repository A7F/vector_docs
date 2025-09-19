[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinMostAMSReportEvent.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMostAMSReportEvent

# TestJoinMostAMSReportEvent

Valid for: CANoe DE

## Function Syntax

- `long TestJoinMostAMSReportEvent (int aFBlockId, int aInstanceId, int aFunctionId)`
- `long TestJoinMostAMSReportEvent (char[] aSymbolicMessage, int aInstanceId)`
- `long TestJoinMostAMSReportEvent (char[] aSymbolicMessage)`

## Description

Completes the current set of "joined events" with the transmitted event, a MOST AMS response message (Report, OpType > 8). This function does not wait.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - FBlock.InstanceId.Function
  - FBlock.Function
  - FBlock

(see also [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md))

## Return Values

- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed
- **-3**: Join error
- **-1**: General error e.g. the functionality is not available
- **> 0**: Number of joined events

## Example

—

[TestJoinMostAMSSpyReportEvent](CAPLfunctionTestJoinMostAMSSpyReportEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForMostAMSMessage](CAPLfunctionTestWaitForMostAMSMessage.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [TestJoinMostAMSMessageEvent](CAPLfunctionTestJoinMostAMSMessageEvent.md) • [TestGetWaitEventMostAMSMsgData](CAPLfunctionTestGetWaitEventMostAmsMsgData.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
