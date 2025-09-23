[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostAmsResponse.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostAMSResponse

# TestWaitForMostAMSResponse

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestWaitForMostAMSResponse (int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostAMSResponse (char[] aSymbolicMessage, int aInstanceId, unsigned long aTimeout);`
- `long TestWaitForMostAMSResponse (char[] aSymbolicMessage, unsigned long aTimeout);`
- `long TestWaitForMostAMSResponse (int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId);`
- `long TestWaitForMostAMSResponse (char[]aSymbolicMessage);`

## Description

This function immediately sends a symbolically defined MOST message and waits for the appropriate response message from the receiver. Thus, it combines the functionalities of [TestSendMostAMSMessage](CAPLfunctionTestSendMostAmsMessage.md) and [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) into one function call. The response message can be read and evaluated after the return of the wait operation using [TestGetWaitEventMostAMSMsgData](CAPLfunctionTestGetWaitEventMostAmsMsgData.md).

The symbolically defined messages must be complete, which means all mandatory data must be specified explicitly (without use of wildcards), because an actual message is sent. However, a parameter list may be shorter than specified in the function catalog, in order to be able to generate intentionally incomplete messages.

If possible, the message is always sent via the AMS service. However, if this is not activated, the message - if short enough - will be sent as a normal control message (with TelID = 0).

If the message is longer than a control message, the function delivers the return value of -5 and a wait point is not set up.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDestinationAddress**: Target address  
  **Note:** If -1 is given, the address handler (if active) searches for the correct node address based on the functional address {FBlockID, InstID} from the Bus Registry. If no node address is found the message is sent to 0xFFFF. This is also the standard for not explicit set values.

- **aInstanceId**: Numeric value of InstanceID  
  **Note:** If -1 is given, the corresponding field can get any value. This is also the standard for not explicit set values.

- **aTimeout**: Maximum wait time [ms]  
  (Transmission of 0: no timeout controlling; test module waits infinitely long)

- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - FBlock.InstanceID.Function.OpType(Parameterliste)
  - FBlock.InstanceID.Function.OpType
  - FBlock.Function.OpType(Parameterliste)
  - FBlock.Function.OpType

  An entry without parameter list yields an empty parameter list (see also [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)).

## Return Values

- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed.
- **-5**: The message is too long and had to be sent using the AMS service, but the AMS service is not activated.
- **-4**: Entered message definition is faulty and could not be resolved
- **-3**: Message was sent, however "not acknowledge" appears in the Tx acknowledgment.
- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **-10**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - 0x1: FBlockID not available
  - 0x2: InstanceID not available
  - 0x3: FktID not available
  - 0x4: OpType not available

  You can find more information about the error codes in the MOST specification.

- **-11**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - 0x5: Invalid length
  - 0x6: Wrong parameter
  - 0x8: Parameter missing
  - 0x9: Too many parameters

- **-12**: The given MOST message was sent, but the receiver responded with an error message that contains one of the following error codes:
  - 0x7: Parameter not available
  - 0x40: Busy
  - 0x041: Not available

- **-13**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x42 (Processing Error).
- **-14**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x20 (Function specific).
- **-15**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0A (Secondary node).
- **-16**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0B (Device malfunction).
- **-17**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x0C (Segmentation error).
- **-18**: The given MOST message was sent, but the receiver responded with an error message that contains the error code 0x43 (Method aborted).
- **0**: Resume based on Timeout
- **1**: Message was sent successfully and the appropriate response received

## Example

—

[Related Links](CAPLfunctionTestSendMostAmsMessage.md) • [TestWaitForMostMessage](CAPLfunctionTestWaitForMostMessage.md) • [TestWaitForMostAMSMessage](CAPLfunctionTestWaitForMostAMSMessage.md) • [TestWaitForMostReport](CAPLfunctionTestWaitForMostReport.md) • [TestWaitForMostAMSResult](CAPLfunctionTestWaitForMostAmsResult.md) • [TestWaitForMostAMSReport](CAPLfunctionTestWaitForMostAMSReport.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)
