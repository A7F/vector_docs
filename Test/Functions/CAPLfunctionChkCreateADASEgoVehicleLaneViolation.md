# ChkCreate_ADASEgoVehicleLaneViolation, ChkStart_ADASEgoVehicleLaneViolation

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `dword chkCreate_ADASEgoVehicleLaneViolation(); //form 1`
- `dword chkCreate_ADASEgoVehicleLaneViolation(char* callback); //form 2`
- `dword chkStart_ADASEgoVehicleLaneViolation(); //form 3`
- `dword chkStart_ADASEgoVehicleLaneViolation(char* callback); //form 4`

## Constructor

- `TestCheck::CreateADASEgoVehicleLaneViolation();`
- `TestCheck::CreateADASEgoVehicleLaneViolation(char* callback);`
- `TestCheck::StartADASEgoVehicleLaneViolation();`
- `TestCheck::StartADASEgoVehicleLaneViolation(char* callback);`

## Check Name

[ADAS EgoLane Observation](../../../TestCommands/CheckDescriptions/CDADASEgoVehicleLaneViolation.md)

## Description

Observes the lane of the EgoVehicle. The check fires an event if the EgoVehicle leaves its lane.

## Parameters

- **callback**: This parameter is optional.
  - Name of the callback which is called when the check fails.
  - Signature: `void Callback( dword checkId )` or `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced.
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- EgoVehicle is undefined.
- CAPL callback does not exist.

## Example

```plaintext
dword checkId1;
checkId1 = chkStart_ADASEgoVehicleLaneViolation();

TestAddCondition(checkId1);
// sequence of different actions and waiting conditions
TestWaitForTimeout(3000);
// ...
TestRemoveCondition(checkId1);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
