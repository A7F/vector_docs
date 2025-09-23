# TestWaitForMostAMSResult

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostAMSResult(long aDestinationAddress, char aSymbolicMessage[], long aInstanceID, dword aTimeoutMaxDuration, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2);`
- `long TestWaitForMostAMSResult(long aDestinationAddress, char aSymbolicMessage[], long aInstanceID, dword aTimeoutMaxDuration);`
- `long TestWaitForMostAMSResult(char aSymbolicMessage[], long aInstanceID, dword aTimeoutMaxDuration);`
- `long TestWaitForMostAMSResult(char aSymbolicMessage[], dword aTimeoutMaxDuration);`
- `long TestWaitForMostAMSResult(char aSymbolicMessage[], long aInstanceID, dword aTimeoutMaxDuration, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2);`
- `long TestWaitForMostAMSResult(char aSymbolicMessage[],dword aTimeoutMaxDuration, dword aTimeoutWaitForProcessing1, dword aTimeoutWaitForProcessing2);`

## Description

The function immediately sends a symbolically defined MOST message with OpType 'StartResult' or 'StartResultAck' and waits for the reception of the appropriate 'Result' or 'ResultAck' message from the receiver.

In contrast to the functionality provided by [TestWaitForMostAMSResponse](CAPLfunctionTestWaitForMostAmsResponse.md), this function checks the correct reception of intermediate ‘Processing’ or ‘ProcessingAck’ as well as the final ‘Result’ or ‘ResultAck’ messages using the provided timeouts for tWaitForProcessing1 and tWaitForProcessing2. Signatures without these timeout parameters use the default values specified in the MOST Specification (tWaitForProcessing1 = 250ms and tWaitForProcessing2. = 200ms).

Additionally, in case of the 'StartResultAck' optype, the SenderHandle parameter is constantly checked for each report message received. Messages having a different SenderHandle than specified in the function call are ignored, since they must belong to a different request for that method.

As soon as a report message doesn’t arrive within the specified timeouts of tWaitForProcessing1 or tWaitForProcessing2, the function resumes and reports a timeout for that parameter.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDestinationAddress**: Target address
  - **Note:** If -1 is given, the address handler (if active) searches for the correct node address based on the functional address {FBlockID, InstID} from the Bus Registry. If no node address is found the message is sent to 0xFFFF. This is also the standard for not explicit set values.

- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - `FBlock.Instance.Function.StartResult(parameter list)`
  - `FBlock.Instance.Function.StartResult`
  - `FBlock.Function.StartResult(parameter list)`
  - `FBlock.Function.StartResult`
  - `FBlock.Instance.Function.StartResultAck(SenderHandle, parameter list)`
  - `FBlock.Instance.Function.StartResultAck(SenderHandle)`
  - `FBlock.Function.StartResultAck(SenderHandle, parameter list)`
  - `FBlock.Function.StartResultAck(SenderHandle)`

- **aInstanceId**: Numeric value of InstanceID
  - **Note:** If -1 is given, the corresponding field can get any value. This is also the standard for not explicit set values.

- **aTimeoutMaxDuration**: Maximum time [ms] to wait for the reception of a 'Result' ('ResultAck') message.

- **aTimeoutWaitForProcessing1**: Maximum time [ms] to wait for the reception of the first 'Processing' ('ProcessingAck') or immediate 'Result' ('ResultAck') message (tWait-ForProcessing1).

- **aTimeoutWaitForProcessing2**: Maximum time [ms] to wait for the reception of the following 'Processing' ('ProcessingAck') or 'Result' ('ResultAck') message (tWaitFor-Processing2).

## Return Values

- **1**: Message was sent successfully and the appropriate response received
- **0**: Resume based on Timeout
- **-1**: General error e.g. the functionality is not available
- **-2**: Resume based on Constraint Violation
- **-3**: Message was sent, however "not acknowledge" appears in the Tx acknowledgment.
- **-5**: The message is too long and had to be sent using the AMS service, but the AMS service is not activated.
- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed.
- **-7**: Message with unexpected OpType received.
- **-8**: Timeout of aTimeoutWaitForProcessing1 (tWaitForProcessing1)
- **-9**: Timeout of aTimeoutWaitForProcessing2 (tWaitForProcessing2)
- **-10**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - **0x1**: FBlockID not available
  - **0x2**: InstanceID not available
  - **0x3**: FktID not available
  - **0x4**: OpType not available
  - You can find more information about the error codes in the MOST specification.
- **-11**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - **0x5**: Invalid length
  - **0x6**: Wrong parameter
  - **0x8**: Parameter missing
  - **0x9**: Too many parameters
- **-12**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - **0x7**: Parameter not available
  - **0x40**: Busy
  - **0x041**: Not available
- **-13**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x42 (Processing Error).
- **-14**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x20 (Function specific).
- **-15**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0A (Secondary node).
- **-16**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0B (Device malfunction).
- **-17**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0C (Segmentation error).
- **-18**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x43 (Method aborted).

## Example

—

[Related Links](CAPLfunctionTestSendMostAmsMessage.md) • [TestSendMostAMSMessage](CAPLfunctionTestSendMostAmsMessage.md) • [TestWaitForMostMessage](CAPLfunctionTestWaitForMostMessage.md) • [TestWaitForMostAMSMessage](CAPLfunctionTestWaitForMostAMSMessage.md) • [TestWaitForMostReport](CAPLfunctionTestWaitForMostReport.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)
