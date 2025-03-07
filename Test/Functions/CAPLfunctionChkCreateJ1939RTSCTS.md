[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateJ1939RTSCTS.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_J1939RTSCTS, ChkStart_J1939RTSCTS

# ChkCreate_J1939RTSCTS, ChkStart_J1939RTSCTS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_J1939RTSCTS(dword t1, dword t2, dword t3, dword t4, char[] callback1);`
- `dword ChkCreate_J1939RTSCTS(dword senderAddress, dword responderAddress, dword t1, dword t2, dword t3, dword t4, char[] callback1);`
- `dword ChkCreate_J1939RTSCTS(Node origninatorNode, Node responderNode, dword t1, dword t2, dword t3, dword t4, char[] callback1);`
- `dword ChkStart_J1939RTSCTS(dword t1, dword t2, dword t3, dword t4, char[] callback1);`
- `dword ChkStart_J1939RTSCTS(dword orginatorAddress, dword responderAddress, dword t1, dword t2, dword t3, dword t4, char[] callback1);`
- `dword ChkStart_J1939RTSCTS(Node origninatorNode, Node responderNode, dword t1, dword t2, dword t3, dword t4, char[] callback1);`

## Constructor

[TestCheck:: CreateJ1939RTSCTS](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck:: CreateJ1939RTSCTS(dword t1, dword t2, dword t3, dword t4, char[] callback2);`
- `TestCheck:: CreateJ1939RTSCTS(dword orginatorAddress, dword responderAddress, dword t1, dword t2, dword t3, dword t4, char[] callback2);`
- `TestCheck:: CreateJ1939RTSCTS(Node origninatorNode, Node responderNode, dword t1, dword t2, dword t3, dword t4, char[] callback2);`

## Check Name

[J1939 RTS/CTS (Check Description)](../../../TestCommands/CheckDescriptions/CDJ1939RTSCTS.md)

## Description

Observes the RTS/CTS transport protocol. It is possible to observe all RTS/CTS transmissions or only the transmission of a specific send node.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **originatorNode**: Originator node from database.
- **responderNode**: Responder node from database.
- **originatorAddress**: Originator address
  - Possible values:
    - 0 – 253: Observe originator node with this address
    - 254, -1 (or 0xFFFFFFFF): Observe all originator nodes
- **responderAddress**: Responder address
  - Possible values:
    - 0 – 253, 255: Observe responder node with this address
    - 254, -1 (or 0xFFFFFFFF): Observe all responder nodes
- **t1**: Timeout T1 [ms] (Default 750ms)
- **t2**: Timeout T2 [ms] (Default 1250ms)
- **t3**: Timeout T3 [ms] (Default 1250ms)
- **t4**: Timeout T4 [ms] (Default 1050ms)
- **callback1**: This parameter is optional. Name of the callback which is called when the check fails.
  - Signature: `void Callback( dword checkId )`
- **callback2**: This parameter is optional. Name of the callback which is called when the check fails.
  - Signature: `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Specified node object does not exist in the database.
- Invalid originator or responder address.
- CAPL callback does not exist.

## Example

```c
// checks the RTS/CTS transport protocol between node N1 and node N2
checkId = ChkStart_J1939RTSCTS(N1, N2, 750, 1250, 1250, 1050);
TestAddCondition(checkId);

// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)