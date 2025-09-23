# ChkCreate_AllNodesBabbling, ChkStart_AllNodesBabbling

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_AllNodesBabbling (Duration aMinQuietTime, char [] CaplCallback);`
- `dword ChkStart_AllNodesBabbling (Duration aMinQuietTime, char [] CaplCallback);`

## Constructor

[TestCheck::CreateAllNodesBabbling](../../../Shared/CAPL/General/ClassesAndObjects.md) (Duration aMinQuietTime, char [] CaplCallback);

## Check Name

[Node Inactive (Check Description)](../../../TestCommands/CheckDescriptions/CDNodeInactive.md)

## Description

There is a time interval where transmissions are tolerated. After the interval has been passed, all nodes may no longer send messages. From now on, each transmission of the nodes is reported.

If the min. quiet time is 0, then each message sent by any node leads to the event.

**Possible application:**

- Supervises the end of a communication.
- Supervises the transition of nodes’ or buses’ state to "sleep active".

Gateway nodes require that the bus context corresponds to the network that is being observed.

For FlexRay only valid data frames and PDUs are recognized as communication, Null Frames and Erroneous frames are ignored.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aMinQuietTime**: \> 0; default unit [ms], if not changed with [ChkConfig_SetPrecision](CAPLfunctionChkConfigSetPrecision.md).
- **CaplCallback**: In simulation nodes this parameter has to be set. In test modules this parameter is optional.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Check-specific Queries

- [ChkQuery_EventInterval](CAPLfunctionChkQueryEventInterval.md)
- [ChkQuery_EventMessageId](CAPLfunctionChkQueryEventMessageId.md)
- [ChkQuery_EventMessageName](CAPLfunctionChkQueryEventMessageName.md)

## Example

```c
// checks that after 300 ms no transmission are available
checkId = ChkStart_AllNodesBabbling(300);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
