# ChkCreate_NodeBabbling, ChkStart_NodeBabbling

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_NodeBabbling (Node n, Duration aMinQuietTime, char [] CaplCallback); // form 1`
- `dword ChkStart_NodeBabbling (Node n, Duration aMinQuietTime, char [] CaplCallback); // form 2`
- `dword ChkStart_NodeBabbling (char [] Node, Duration aMinQuietTime, char [] CaplCallback); // form 3`

## Constructor

[TestCheck::CreateNodeBabbling (Node n, Duration aMinQuietTime, char [] CaplCallback); // form 1](../../../Shared/CAPL/General/ClassesAndObjects.htm)

- `TestCheck::StartNodeBabbling (Node n, Duration aMinQuietTime, char [] CaplCallback); // form 2`
- `TestCheck::StartNodeBabbling (char [] Node, Duration aMinQuietTime, char [] CaplCallback); // form 3`

## Check Name

[Node Inactive (Check Description)](../../../TestCommands/CheckDescriptions/CDNodeInactive.md)

## Description

This check supervises the end of a communication: There is a time interval where node-transmissions are tolerated. After the interval has been passed, the node may no longer send messages. From now on, each transmission of the node is reported.

If the min. quiet time is 0, then each message sent by the node leads to the event.

**Use Cases**:  
Supervise the transition of nodes’ or buses’ state to 'sleep active'.

Gateway nodes require that the bus context corresponds to the bus that is being observed. This means that the check only works correctly if the current bus context corresponds to the database in which the node is defined.

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **n/Node**: Defined node in database.
- **aMinQuietTime**: \> 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **CaplCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```c
// checks that after 300 ms no transmission of the node is available
checkId = ChkStart_NodeBabbling(NodeToObserve, 300);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
