[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateJ1939BAM.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_J1939BAM, ChkStart_J1939BAM

# ChkCreate_J1939BAM, ChkStart_J1939BAM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_J1939BAM(dword min, dword max, char[] callback1);`
- `dword ChkCreate_J1939BAM(dword originatorAddress, dword min, dword max, char[] callback1);`
- `dword ChkCreate_J1939BAM(Node origninatorNode, dword min, dword max, char[] callback1);`
- `dword ChkStart_J1939BAM(dword min, dword max, char[] callback1);`
- `dword ChkStart_J1939BAM(dword orginatorAddress, dword min, dword max, char[] callback1);`
- `dword ChkStart_J1939BAM(Node origninatorNode, dword min, dword max, char[] callback1);`

## Constructor

[TestCheck::CreateJ1939BAM](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateJ1939BAM (dword min, dword max, char[] callback2);`
- `TestCheck::CreateJ1939BAM (dword orginatorAddress, dword min, dword max, char[] callback2);`
- `TestCheck::CreateJ1939BAM (Node origninatorNode, dword min, dword max, char[] callback2);`

## Check Name

[J1939 BAM (Check Description)](../../../TestCommands/CheckDescriptions/CDJ1939BAM.md)

## Description

Observes the BAM transport protocol. It is possible to observe all BAM transmissions or only the transmission of a specific originator node.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **originatorNode**: Originator node from database
- **originatorAddress**: Originator address
  - Possible values:
    - 0 – 253: Observe originator node with this address
    - 254, -1 (or 0xFFFFFFFF): Observe all nodes
- **min**: Minimum distance [ms] (Default 50ms)
- **max**: Maximum distance [ms] (Default 200ms)
- **callback1**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( dword checkId )`
- **callback2**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Specified node object does not exist in the database.
- Invalid originator address.
- CAPL callback does not exist.

## Example

```plaintext
// checks the BAM transport protocol of node N1
checkId = ChkStart_J1939BAM(N1, 100, 200);
TestAddCondition(checkId);

// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
