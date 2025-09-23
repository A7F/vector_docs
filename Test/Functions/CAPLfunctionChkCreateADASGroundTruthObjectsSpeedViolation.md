[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsSpeedViolation.md)

**CAPL Functions** » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_ADASGroundTruthObjectsSpeedViolation, chkStart_ADASGroundTruthObjectsSpeedViolation

# ChkCreate_ADASGroundTruthObjectsSpeedViolation, chkStart_ADASGroundTruthObjectsSpeedViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Changes**

This function was renamed from **chkCreate_ADASSpeedToObjectsViolation**/**chkStart_ADASSpeedToObjectsViolation** in version 16 SP3.

## Function Syntax

- `dword chkCreate_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold); // form 1`
- `dword chkCreate_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, char* callback); // form 2`
- `dword chkCreate_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); // form 3`
- `dword chkCreate_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); // form 4`
- `dword chkStart_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold); // form 5`
- `dword chkStart_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, char* callback); // form 6`
- `dword chkStart_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); // form 7`
- `dword chkStart_ADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); // form 8`

## Constructor

- `TestCheck::CreateADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold);`
- `TestCheck::CreateADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::CreateADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::CreateADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold);`
- `TestCheck::StartADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::StartADASGroundTruthObjectsSpeedViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`

## Check Name

[ADAS Ground Truth Objects Speed Observation](../../../TestCommands/CheckDescriptions/CDADASGroundTruthObjectsSpeedObservation.md)

## Description

Observes the relative speed of the Moving Objects to the EgoVehicle. The check fires an event if the speed conditions passed as arguments are fulfilled.

## Parameters

- **overUnder**: Specifies if the distance violation is over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum speed. An object moving towards the EgoVehicle has a negative relative speed. An object moving away from the EgoVehicle has a positive relative speed. The speed is specified in m/s.
- **laneId**: Only Moving Objects on the lane with the given laneId will be checked. If no laneId is given or the laneId is -1, only the lane of the EgoVehicle will be considered.
- **movingObjectId**: GroundTruthId of the moving object. Only the distance to this Moving Object will be checked. If the value -1 is given, all Moving Objects will be checked.
- **callback**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( dword checkId )` or `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- EgoVehicle is undefined.
- CAPL callback does not exist.

## Example

```c
enum OverUnder
{
    kUnder = 0,
    kOver = 1
};

dword checkId1, checkId2;
checkId1 = chkStart_ADASGroundTruthObjectsSpeedViolation(kUnder, 10.0); // relative speed under 10 m/s to EgoVehicle of any Moving Object will trigger the check
checkId2 = chkStart_ADASGroundTruthObjectsSpeedViolation(kOver, 50.0, 2, 100); // relative speed over 50 m/s from EgoVehicle to Moving Object with ID 100 on lane with ID 2 will trigger the check

TestAddCondition(checkId1);
TestAddCondition(checkId2);
// sequence of different actions and waiting conditions
TestWaitForTimeout(3000);
TestRemoveCondition(checkId1);
TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
