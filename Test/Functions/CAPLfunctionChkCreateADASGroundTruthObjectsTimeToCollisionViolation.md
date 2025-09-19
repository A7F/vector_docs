[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsTimeToCollisionViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_ADASGroundTruthObjectsTimeToCollisionViolation, ChkStart_ADASGroundTruthObjectsTimeToCollisionViolation

# ChkCreate_ADASGroundTruthObjectsTimeToCollisionViolation, ChkStart_ADASGroundTruthObjectsTimeToCollisionViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Changes
This function was renamed from **chkCreate_ADASTimeToImpactViolation**/**chkStart_ADASTimeToImpactViolation** in version 16 SP3.

## Function Syntax

- `dword chkCreate_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold); // form 1`
- `dword chkCreate_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback); // form 2`
- `dword chkCreate_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); // form 3`
- `dword chkCreate_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); // form 4`
- `dword chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold); // form 5`
- `dword chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback); // form 6`
- `dword chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); // form 7`
- `dword chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); // form 8`

## Constructor

- `TestCheck::CreateADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold);`
- `TestCheck::CreateADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::CreateADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::CreateADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold);`
- `TestCheck::StartADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::StartADASGroundTruthObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`

## Check Name

[ADAS Ground Truth Objects Time To Collision Observation](../../../TestCommands/CheckDescriptions/CDADASGroundTruthObjectsTimeCollisionObservation.md)

## Description

Observes the Time To Collision (TTC) between Moving Objects and the EgoVehicle. The check fires an event if the TTC conditions passed as arguments are fulfilled.

## Parameters

- **overUnder**: Specifies if the distance violation is over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum TTC. The distance is specified in meter.
- **laneId**: Only Moving Objects on the lane with the given laneId will be checked. If no laneId is given or the laneId is -1, only the lane of the EgoVehicle will be considered.
- **movingObjectId**: GroundTruthId of the moving object. Only the distance to this Moving Object will be checked. If the value -1 is given, all Moving Objects will be checked.
- **callback**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( dword checkId )` or `void Callback( TestCheck check )`

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- EgoVehicleId is undefined.
- CAPL callback does not exist.

## Example

```c
enum OverUnder
  {
    kUnder = 0,
    kOver = 1
  };

dword  checkId1, checkId2;
checkId1 = chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (kUnder, 1.0); // TTI under 1s to EgoVehicle of any Moving Object will trigger the check
checkId2 = chkStart_ADASGroundTruthObjectsTimeToCollisionViolation (kOver, 5.0, 2, 100); // TTI over 5s from EgoVehicle to Moving Object with ID 100 on lane with ID 2 will trigger the check

TestAddCondition(checkId1);
TestAddCondition(checkId2);
// sequence of different actions and waiting conditions
TestWaitForTimeout(3000);
TestRemoveCondition(checkId1);
TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
