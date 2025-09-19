[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateNodeMsgsRelCycleTimeViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » ChkCreate_NodeMsgsRelCycleTimeViolation, ChkStart_NodeMsgsRelCycleTimeViolation

# ChkCreate_NodeMsgsRelCycleTimeViolation, ChkStart_NodeMsgsRelCycleTimeViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword ChkCreate_NodeMsgsRelCycleTimeViolation (Node aNode, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);
dword ChkStart_NodeMsgsRelCycleTimeViolation (Node aNode, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);
```

## Constructor

[TestCheck::CreateNodeMsgsRelCycleTimeViolation](../../../Shared/CAPL/General/ClassesAndObjects.md) (Node aNode, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);

[TestCheck::StartNodeMsgsRelCycleTimeViolation](../../../Shared/CAPL/General/ClassesAndObjects.md) (Node aNode, double aMinRelCycleTime, double aMaxRelCycleTime, Callback aCallback);

## Check Name

[Cycle Time](../../../TestCommands/CheckDescriptions/CDCycleTime.md)

## Description

Checks the occurrences of cyclic messages of the given send node.

Event is generated if the time between sends of the (same) message is smaller than minRelCycleTime *GenMsgCycleTime (DB-attribute) or larger than maxRelCycleTime* GenMsgCycleTime.

Not to be checked limits are set to 0; there must be at least one limit specified.

Not checked are send messages with a specified cycle time equal to 0 or network management messages or diagnostic messages.

Can be started only in the start-section of CAPL or during measurement.

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Must exist in DB
- **aMinRelCycleTime**:
  - 0: Limit is not checked
  - 0 < x < 1: Limit is checked
- **aMaxRelCycleTime**:
  - 0: Limit is not checked
  - 1 < x < ∞: Limit is checked
- **aCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value

## Possible Errors

- Value range(s) exceeded
- Node object does not exist in the DB
- There are no cyclic messages in the specified node
- There are messages specified as cyclic but the cycle time is 0 or not available
- Both relative limits are 0
- CAPL callback does not exist

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```cpp
// checks the cycle time of all messages of the node
checkId = ChkStart_NodeMsgsRelCycleTimeViolation(NodeToObserve, 0.9, 1.1);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
