# ChkCreate_MostMethodProtocolError, ChkStart_MostMethodProtocolError

[Valid for CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

- `dword ChkCreate_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration, Callback aCallback);`
- `dword ChkCreate_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration);`
- `dword ChkStart_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration);`

## Constructor

- `TestCheck::CreateMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::CreateMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `TestCheck::CreateMostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::CreateMostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2, dword aTimeoutMaxDuration);`
- `TestCheck::CreateMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::CreateMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration);`
- `TestCheck::StartMostMethodProtocolError(char aMethod[], long aInstanceID, dword aTimeoutMaxDuration);`
- `TestCheck::Create_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::Start_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration, Callback aCallback);`
- `TestCheck::Create_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration);`
- `TestCheck::Start_MostMethodProtocolError(char aMethod[], dword aTimeoutMaxDuration);`

## Check Name

[MOST Method Protocol Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDMOSTMethodProtocolObservation.md)

## Description

This check monitors MOST protocol compliance for a given method supporting the optypes "StartResult" or "StartResultAck". This includes monitoring of the messages sequences and timeout conditions on answer times and send intervals.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMethod**: Name of the method to be monitored in one of the following formats:
  - FBlock.InstanceID.Function
  - FBlock.Function

- **aInstanceID**: InstanceID of the method to be monitored. Since command messages are often addressed to wildcard InstanceID (0x00) it is recommended to set this parameter to 0x00. The check includes requests/responses with InstanceIDs from 0x00 to 0xFE then. If a signature without InstanceID parameter is chosen, 0x00 is applied. InstanceID=0xFF=All observes requests with InstanceID=0xFF only. In this case it cannot be checked if all FBlock instances reply, because the number of instances in a device is not known to the algorithm.

- **aTimeoutWaitForProcessing1**: Timeout to wait for the observation of the first "Processing" or "ProcessingAck" message. The unit can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md). Signatures that do not provide this parameter, assume the maximum value of 250 ms given for tWaitForProcessing1 in the MOST specification.

- **aTimeoutWaitForProcessing2**: Timeout to wait for the following Processing messages. The unit can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md). Signatures that do not provide this parameter, assume the typical value of 200 ms given for tWaitForProcessing2 in the MOST specification.

- **aTimeoutMaxDuration**: Maximum response time for the observed method to return a "Result"/ "ResultAck" or "Error"/ "ErrorAck" message. The unit can be set with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

- **aCallback**: Name of the callback function, which should be called as soon as a protocol violation is detected. In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- CAPL callback does not exist.

## Check-specific Queries

- [ChkQuery_NumRequests](CAPLfunctionChkQueryNumRequests.md)
- [ChkQuery_NumTimedoutRequests](CAPLfunctionChkQueryNumTimedoutRequests.md)
- [ChkQuery_RequestDstAdr](CAPLfunctionChkQueryRequestDstAdr.md)
- [ChkQuery_RequestFBlockId](CAPLfunctionChkQueryRequestFBlockId.md)
- [ChkQuery_RequestFunctionId](CAPLfunctionChkQueryRequestFunctionId.md)
- [ChkQuery_RequestInstId](CAPLfunctionChkQueryRequestInstId.md)
- [ChkQuery_RequestOpType](CAPLfunctionChkQueryRequestOpType.md)
- [ChkQuery_RequestSrcAdr](CAPLfunctionChkQueryRequestSrcAdr.md)
- [ChkQuery_RequestTimestamp](CAPLfunctionChkQueryRequestTimestamp.md)
- [ChkQuery_StatAvResponseTime](CAPLfunctionChkQueryStatAvResponseTime.md)
- [ChkQuery_StatMaxValidResponseTime](CAPLfunctionChkQueryStatMaxValidResponseTime.md)

## Example

—

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
