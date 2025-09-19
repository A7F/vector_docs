[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostSpyMessage.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForMostSpyMessage**

# TestWaitForMostSpyMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostSpyMessage(dbMsg aDBMsg, int aInstanceId, dword aTimeout);`
- `long TestWaitForMostSpyMessage(int aFBlockId, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(int aFBlockId, int aInstanceId, int aFunctionId, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(int aFBlockId, int aInstanceId, int aFunctionId, int aOpType, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(int aSourceAddress, int aDestinationAddress, int aFBlockId, int aInstanceId, int aFunctionId, int aOpType, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(int aSourceAddress, int aDestinationAddress, char[] aSymbolicMessage, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostSpyMessage(char[] aSymbolicMessage, unsigned long aTimeout);`

## Description

Waits for the occurrence of the specified MOST Spy message. The first arriving control message, which fulfills the specified conditions, resolves the delay point, irregardless of whether it is part of a segmented transmission. TelId is not included in this process. If the message does not occur by the time the **aTimeout** expires, the wait condition is still resolved.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDBMsg**: MOST function catalog MOST message (e.g. AudioDiskPlayer.TrackPosition.Status) or message name from CANdb database (e.g. ADP_TrackPosition_Status).
- **aSourceAddress**: Source address
- **aDestinationAddress**: Target address
- **aFBlockId**: Numeric value of FBlockID
- **aInstanceId**: Numeric value of InstanceID
- **aFunctionId**: Numeric value of FunctionID
- **aOpType**: Numeric value of OpTypes
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring; test module waits infinitely long)
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

[Related Links:](CAPLfunctionTestWaitForMostAMSSpyMessage.md) TestWaitForMostAMSSpyMessage • [TestWaitForMostMessage](CAPLfunctionTestWaitForMostMessage.md) • [TestJoinMostSpyReportEvent](CAPLfunctionTestJoinMostSpyReportEvent.md) • [TestWaitForMostSpyReport](CAPLfunctionTestWaitForMostSpyReport.md) • [TestGetWaitEventMostMsgData](CAPLfunctionTestGetWaitEventMostMsgData.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
