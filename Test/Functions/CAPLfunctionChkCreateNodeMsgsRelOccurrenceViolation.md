[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateNodeMsgsRelOccurrenceViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_NodeMsgsRelOccurrenceViolation, ChkStart_NodeMsgsRelOccurrenceViolation

# ChkCreate_NodeMsgsRelOccurrenceViolation, ChkStart_NodeMsgsRelOccurrenceViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword ChkCreate_NodeMsgsRelOccurrenceViolation(Node observedNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);
dword ChkStart_NodeMsgsRelOccurrenceViolation(Node observedNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);
```

## Constructor

[TestCheck::CreateNodeMsgsRelOccurrenceViolation](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
TestCheck::CreateNodeMsgsRelOccurrenceViolation(Node observedNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);
TestCheck::StartNodeMsgsRelOccurrenceViolation(Node observedNode, double aMinRelCycleTime, double aMaxRelCycleTime, char[] aCallback);
```

## Check Name

[Occurrence Of Messages (Check Description)](../../../TestCommands/CheckDescriptions/CDOccurrenceOfMessages.md)

## Description

Checks for the occurrence of periodic message of the specified send node. The check condition is violated if the time between transmissions of the message is less than aMinRelCycleTime *GenMsgDelayTime or greater than aMaxRelCycleTime* Cycle Time. Cycle time is calculated from GenMsgCycleTime and GenSigCycleTime. Limits that should not be checked must be set to 0. At least one limit must be specified. Can only be started in the "on start" area of CAPL or during the measurement. However, the check may be set up as early as in the "pre start" area.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **observedNode**: Must exist in the database.
- **aminRelCycleTime**:
  - 0: Limit is not checked.
  - 0 < x < 1: Limit is checked.
- **aMaxRelCycleTime**:
  - 0: Limit is not checked.
  - 1 < x < ∞: Limit is checked.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.

## Return Values

- **0**: Check could not be created and may not be referenced.
- **> 0**: Check was created successfully and can be referenced with the help of the returned (Handle) value.

## Possible Errors

- Value(s) outside of value range(s).
- Specified node object does not exist in the database.
- No periodic messages exist in the specified node.
- Messages were specified as cyclic, but their cycle times are either 0 or unavailable.
- Both relative limits are 0.
- CAPL Callback does not exist.

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```cpp
// checks the periodic occurrence of all messages of the node
checkId = ChkStart_NodeMsgsRelOccurrenceViolation(NodeToObserve, 0.9, 1.1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
