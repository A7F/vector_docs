[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestSendMostAmsMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestSendMostAMSMessage

# TestSendMostAMSMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long TestSendMostAMSMessage(int aDestinationAddress, char[] aSymbolicMessage, int aInstanceId);`
- `long TestSendMostAMSMessage(char[] aSymbolicMessage, int aInstanceId);`
- `long TestSendMostAMSMessage(char[] aSymbolicMessage);`

## Description

This function immediately sends a symbolically-defined MOST message and waits for the associated Tx acknowledgment from the recipient. The AckNack bit is evaluated and the return value specifies whether the creation and sending of the message was successful or not.

The symbolically-defined messages must be complete, that is, all absolutely necessary details must be specified explicitly (without the use of wildcards) since a concrete message will be sent. However, a parameter list may be shorter than specified in the function catalog in order to be able to generate incomplete messages purposefully.

If possible, the message is always sent using the AMS service. However, if this is not activated, the message, if short enough, will be sent as a normal control message (with TelID = 0).

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aDestinationAddress**: Target address
  - **Note:** If -1 is given, the address handler (if active) searches for the correct node address based on the functional address {FBlockID, InstID} from the Bus Registry. If no node address is found the message is sent to 0xFFFF. This is also the standard for not explicit set values.

- **aSymbolicMessage**: Symbolic MOST message definition in one of the following formats:
  - `FBlock.Instance.Function.OpType(parameter list)`
  - `FBlock.Instance.Function.OpType`
  - `FBlock.Function.OpType(parameter list)`
  - `FBlock.FunctionId.OpType`

- **aInstanceId**: Numeric specification of the InstanceID
  - **Note:** If -1 is given, the corresponding field can get any value. This is also the standard for not explicit set values.

## Return Values

- **-6**: Parse Error; on specification of a symbolic message definition that cannot be resolved with the available XML function catalog or that is flawed
- **-5**: The message is too long and had to be sent using the AMS service, but the AMS service is not activated.
- **-3**: Message was sent, however "not acknowledge" appears in the Tx acknowledgment.
- **-2**: The wait condition was triggered due to a constraint violation.
- **-1**: General error, for example, the functionality is not available
- **0**: Resume due to timeout
- **1**: Message could be sent, Tx acknowledgment received

## Example

—

[TestSetSendTimeout](CAPLfunctionTestSetSendTimeOut.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)
