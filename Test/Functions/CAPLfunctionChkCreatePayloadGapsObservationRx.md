# ChkCreate_PayloadGapsObservationRx, ChkStart_PayloadGapsObservationRx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword ChkCreate_PayloadGapsObservationRx(Node aNode, long defaultBitValue, char [] aCallback);`
- `dword ChkStart_PayloadGapsObservationRx(Node aNode, long defaultBitValue, char [] aCallback);`

## Constructor

[TestCheck::CreatePayloadGapsObservationRx(Node aNode, long defaultBitValue, char [] aCallback);](../../../Shared/CAPL/General/ClassesAndObjects.htm)

[TestCheck::StartPayloadGapsObservationRx(Node aNode, long defaultBitValue, char [] aCallback);](../../../Shared/CAPL/General/ClassesAndObjects.htm)

## Check Name

[Payload Gaps Observation (Check Description)](../../../TestCommands/CheckDescriptions/CDPayloadGapsObservation.md)

## Description

Checks the payload gaps and the DLC of all Rx messages of a node. The check condition is violated if the payload gaps do not match the specified default bit value or the DLC does not match the specified DLC of the database.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Must exist in the database.
- **defaultBitValue**: Default bit value the payload gaps must have.
- **aCallback**: This parameter must be specified in simulation nodes; it is optional in test modules.

## Return Values

- **0**: Check could not be created and must not be referenced.
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- Specified message object does not exist in the database.
- CAPL Callback does not exist.

## Example

```c
// checks the payload gaps of the message
checkId = ChkStart_PayloadGapsObservationRx(NodeToObserve, 0);
TestAddCondition(checkId);
// sequence of different actions and waiting conditions
TestWaitForTimeout(1000);
TestRemoveCondition(checkId);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
