[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostSpyReport.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostSpyReport

# TestWaitForMostSpyReport

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestWaitForMostSpyReport(int aFBlockId, int aInstanceId, int aFunctionId, unsigned long aTimeout);
long TestWaitForMostSpyReport(char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);
long TestWaitForMostSpyReport(char[] aSymbolicMessage, unsigned long aTimeout);
```

## Description

Waits for the occurrence of the spy response message (report, op-type > 8) of the specified MOST message. The first arriving control message, which fulfills the specified conditions, resolves the wait point, irregardless of whether it is part of a segmented transmission. TelId is not included in this process. If the message does not occur by the time the aTimeout expires, the wait condition is still resolved.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

**Note**: For parameters **aFBlockId**, **aInstanceId** and **aFunctionId** the following applies: If **-1** is given, the corresponding field can get any value. This is also the standard for not explicit set values.

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

[TestWaitForMostAMSSpyReport](CAPLfunctionTestWaitForMostAMSSpyReport.md) • [TestWaitForMostReport](CAPLfunctionTestWaitForMostReport.md) • [TestJoinMostSpyReportEvent](CAPLfunctionTestJoinMostSpyReportEvent.md) • [TestWaitForMostSpyMessage](CAPLfunctionTestWaitForMostSpyMessage.md) • [TestGetWaitEventMsgData](CAPLfunctionTestGetWaitEventMsgData.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
