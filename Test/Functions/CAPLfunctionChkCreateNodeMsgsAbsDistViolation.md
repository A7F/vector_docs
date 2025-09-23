# ChkCreate_NodeMsgsAbsDistViolation, ChkStart_ NodeMsgsAbsDistViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_NodeMsgsAbsDistViolation (Node aNode, Duration aMinTime, long aViolationsMaxCount, Duration aRatingPeriod);`
- `dword ChkStart_NodeMsgsAbsDistViolation (Node aNode, Duration aMinTime, long aViolationsMaxCount, Duration aRatingPeriod);`
- `dword ChkCreate_NodeMsgsAbsDistViolation (Node aNode, Duration aMinTime);`
- `dword ChkStart_NodeMsgsAbsDistViolation (Node aNode, Duration aMinTime);`

## Constructor

- `TestCheck::CreateNodeMsgsAbsDistViolation (Node aNode, Duration aMinTime, long aViolationsMaxCount, Duration aRatingPeriod);`
- `TestCheck::StartNodeMsgsAbsDistViolation (Node aNode, Duration aMinTime, long aViolationsMaxCount, Duration aRatingPeriod);`
- `TestCheck::CreateNodeMsgsAbsDistViolation (Node aNode, Duration aMinTime);`
- `TestCheck::StartNodeMsgsAbsDistViolation (Node aNode, Duration aMinTime);`

## Check Name

[Occurrence Distance (Check Description)](../../../TestCommands/CheckDescriptions/CDOccurrenceDistance.md)

## Description

This check allows the supervision of the minimum send distance of all Tx messages of a node on one bus.

If no rating period and maximal number of distance undercuts is specified, the check condition fails if the time interval between two messages of the node undercuts the **MinTime**.

If the rating period and the maximal number of distance undercuts (\> 0) are specified, the check observes the number of distance undercuts in a time slot. Exceeds the number of distance undercuts the allowed number in a time slot, the check fails.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Must exist in DB. For Gateways the node name has to be prefixed by the bus name.
- **aMinTime**: Minimum send distance of all Tx messages of the node. \> 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **aViolationsMaxCount**: The number of allowed distance undercuts.
- **aRatingPeriod**: Duration of the time slot, in which the maximal allowed number of distance undercuts is checked. \> 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Example

```c
// checks the send distance between all Tx messages of the node
checkId = ChkStart_NodeMsgsAbsDistViolation(NodeToObserve, 30, 2, 40);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
