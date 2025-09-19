[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinMostSpyReportEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinMostSpyReportEvent

# TestJoinMostSpyReportEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `TestJoinMostSpyReportEvent (int aFBlockId, int aInstanceId, int aFunctionId)`
- `TestJoinMostSpyReportEvent (char[] aSymbolicMessage, int aInstanceId)`
- `TestJoinMostSpyReportEvent (char[] aSymbolicMessage)`

## Description

Completes the current set of "joined events" with the transmitted event, a MOST Spy response message (Report, OpType > 8).

The first arriving control message, which fulfills the specified conditions, resolves the wait point, irregardless of whether it is part of a segmented transmission. TelId is not included in this process.

This function does not wait.

The wait point can be subsequently attached with [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) and [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md).

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

**Note:** For parameters **aFBlockId**, **aInstanceId** and **aFunctionId** the following applies: If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

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

[TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestJoinMostAMSSpyReportEvent](CAPLfunctionTestJoinMostAMSSpyReportEvent.md) • [TestJoinMostReportEvent](CAPLfunctionTestJoinMostReportEvent.md) • [TestJoinMostSpyMessageEvent](CAPLfunctionTestJoinMostSpyMessageEvent.md) • [TestWaitForMostSpyMessage](CAPLfunctionTestWaitForMostSpyMessage.md) • [TestGetWaitEventMostMsgData](CAPLfunctionTestGetWaitEventMostMsgData.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
