[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateJ1939Request2.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_J1939Request2, ChkStart_J1939Request2

# ChkCreate_J1939Request2, ChkStart_J1939Request2

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_J1939Request2(Node requestNode, Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkCreate_J1939Request2(Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkCreate_J1939Request2(dword requestSourceAddress, dword responseSourceAddress, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkCreate_J1939Request2(dword requestSourceAddress, dword responseSourceAddress, dword requestedPGN, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkCreate_J1939Request2(Node responseNode, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkStart_J1939Request2(Node requestNode , Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkStart_J1939Request2(Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkStart_J1939Request2(dword requestSourceAddress, dword responseSourceAddress, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkStart_J1939Request2(dword requestSourceAddress, dword responseSourceAddress, dword requestedPGN, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`
- `dword ChkStart_J1939Request2(Node responseNode, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback1);`

## Constructor

[TestCheck::CreateJ1939Request2](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateJ1939Request2(Node requestNode , Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback2);`
- `TestCheck::CreateJ1939Request2(Node responseNode, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback2);`
- `TestCheck::CreateJ1939Request2(dword requestSourceAddress, dword responseSourceAddress, Message requestedMessage, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback2);`
- `TestCheck::CreateJ1939Request2(dword requestSourceAddress, dword responseSourceAddress, dword requestedPGN, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback2);`
- `TestCheck::CreateJ1939Request2(Node responseNode, dword expected, dword options, dword timeout, dword requestInhibitTime, dword retryInhibitTime, char[] callback2);`

## Check Name

[J1939 Request2 Check (Check Description)](../../../TestCommands/CheckDescriptions/CDJ1939Request2Check.md)

## Description

Observes the J1939 Request2 (C900h). It is possible to observe all Request2 messages or only the Request2 message for a specific send node.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **requestNode**: Requesting node from database.
- **responseNode**: Responding node from database.
- **requestSourceAddress**: Address of the ECU which sends the request. Possible values:
  - 0 – 253: Observe request node with this address
  - 254, -1 (or 0xFFFFFFFF): Observe all request nodes
- **responseSourceAddress**: Address of the ECU which sends the response. Possible values:
  - 0 – 253: Observe response node with this address
  - 254, -1 (or 0xFFFFFFFF): Observe all response nodes
- **requestedMessage**: Requested message from database (the parameter group number of this message is used).
- **requestedPGN**: Parameter group number of the requested message.
- **expected**: One or more expected results
  - bit 1: the requested parameter group
  - bit 2: the negative Acknowledgment message
  - bit 3: the positive Acknowledgment message
  - bit 4: the access denied Acknowledgment message
  - bit 5: the address busy Acknowledgment message
  - bit 6: timeout, no answer expected.
  - You can combine the expected parameters by bitwise operations.
- **options**:
  - bit 1: allow request if request is pending
  - bit 2: allow Acknowledgment message sent to specific destination address (required by ISO11783)
  - You can combine the options parameters by bitwise operations.
- **timeout**: Maximum allowed time between request and response (default 1250ms) [ms].
- **requestInhibitTime**: Time, during the last received message, when no request for this message is allowed (default 50ms) [ms].
- **retryInhibitTime**: Time after the last timeout of the second retry (third request) until the same request can be sent again without being recognized as invalid third (default 0ms) [ms].
- **callback1**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( dword checkId )`
- **callback2**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced.
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Specified node object does not exist in the database.
- Specified message object does not exist in the database.
- Invalid request or response address.
- CAPL callback does not exist.

## Example

```plaintext
TestCheck check;
// checks the if a response from N2 is received after a J1939 Request2 from node N1
checkId = ChkStart_J1939Request2(N1, N2, GBSD, 0x01, 0, 1250, 50, 0);
TestAddCondition(checkId);

// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
