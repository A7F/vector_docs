[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostMessage.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForMostMessage**

# TestWaitForMostMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostMessage(dbMsg aDBMsg, int aInstanceId, dword aTimeout);`
- `long TestWaitForMostMessage(int aFBlockId, int aInstanceId, dword aTimeout);`
- `long TestWaitForMostMessage(int aFBlockId, int aInstanceId, int aFunctionId, dword aTimeout);`
- `long TestWaitForMostMessage(int aFBlockId, int aInstanceId, int aFunctionId, int aOpType, dword aTimeout);`
- `long TestWaitForMostMessage(int aSourceAddress, int aDestinationAddress, int aFBlockId, int aInstanceId, int aFunctionId, int aOpType, dword aTimeout);`
- `long TestWaitForMostMessage(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostMessage(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, unsigned long aTimeout);`
- `long TestWaitForMostMessage(char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostMessage(char[] aSymbolicMessage, unsigned long aTimeout);`

## Description

Waits for the occurrence of the specified MOST message (MOST control message or MOST spy message). Should the message not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDBMsg**: MOST function catalog MOST message (e.g. AudioDiskPlayer.TrackPosition.Status) or message name from CANdb database (e.g. ADP_TrackPosition_Status).
- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aOpType**: Numeric value of OpTypes
- **aTimeout**: Maximum wait time [ms] (Transmission of 0: no timeout controlling)
- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - FBlock.InstanceId.Function.OpType(Parameterliste)
  - FBlock.InstanceId.Function.OpType
  - FBlock.Function.OpType(Parameterliste)
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

[TestWaitForMostSpyMessage](CAPLfunctionTestWaitForMostSpyMessage.md) • [TestWaitForMostReport](CAPLfunctionTestWaitForMostReport.md) • [TestJoinMostMessageEvent](CAPLfunctionTestJoinMostMessageEvent.md) • [TestJoinMostReportEvent](CAPLfunctionTestJoinMostReportEvent.md) • [TestGetWaitEventMostMsgData](CAPLfunctionTestGetWaitEventMostMsgData.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
