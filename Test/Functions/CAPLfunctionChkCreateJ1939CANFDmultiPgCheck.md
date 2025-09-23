# ChkCreate_J1939_CANFD_MultiPgCheck, ChkStart_J1939_CANFD_MultiPgCheck

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_J1939_CANFD_MultiPgCheck(Node producerNode, char[] callback1);`
- `dword ChkCreate_J1939_CANFD_MultiPgCheck(dword producerAddress, char[] callback1);`
- `dword ChkStart_J1939_CANFD_MultiPgCheck(Node producerNode, char[] callback1);`
- `dword ChkStart_J1939_CANFD_MultiPgCheck(dword producerAddress, char[] callback1);`

## Constructor

[TestCheck::CreateJ1939_CANFD_MultiPgCheck(Node producerNode, char[] callback2);](../../../Shared/CAPL/General/ClassesAndObjects.htm)
- `TestCheck::CreateJ1939_CANFD_MultiPgCheck(dword producerAddress, char[] callback2);`
- `TestCheck::StartJ1939_CANFD_MultiPgCheck(Node producerNode, char[] callback2);`
- `TestCheck::StartJ1939_CANFD_MultiPgCheck(dword producerAddress, char[] callback2);`

## Description

Observes the validity of transmitted Mult-PGs according to J1939-22 (CAN FD). It is possible to observe Multi-PGs sent by all nodes or only the Multi-PGs sent by a specific node.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.

Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **producerNode**: Producer node from database.
- **producerAddress**: Producer address
  - Possible values:
    - 0 – 253: Observe producer node with this address
    - 254, -1 (or 0xFFFFFFFF): Observe all producer nodes
- **callback1**: This parameter is optional.
  - Name of the callback which is called when the check fails.
  - Signature: `void Callback( dword checkId )`
- **callback2**: This parameter is optional.
  - Name of the callback which is called when the check fails.
  - Signature: `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced.
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Example

```c
dword checkId;
checkId = ChkCreate_J1939_CANFD_MultiPgCheck(N1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[J1939 CAN FD Multi-PG Check (Check Description)](../../../TestCommands/CheckDescriptions/CDJ1939CANFDmultiPgCheck.md) • [Test Service Library: Configuration Functions](../CAPLfunctionsTSLConfigurationFunctions.md) • [Test Service Library: Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
