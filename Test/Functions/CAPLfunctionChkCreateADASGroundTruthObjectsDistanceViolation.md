[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsDistanceViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » ChkCreate_ADASGroundTruthObjectsDistanceViolation, ChkStart_ADASGroundTruthObjectsDistanceViolation

# ChkCreate_ADASGroundTruthObjectsDistanceViolation, ChkStart_ADASGroundTruthObjectsDistanceViolation

[Valid for: CANoe DE • CANoe4SW DE](../../../Shared/FeatureAvailability.md)

## Changes

This function was renamed from **chkCreate_ADASDistanceToObjectsViolation**/**chkStart_ADASDistanceToObjectsViolation** in version 16 SP3.

## Function Syntax

- `dword chkCreate_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold); //form 1`
- `dword chkCreate_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, char* callback); //form 2`
- `dword chkCreate_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); //form 3`
- `dword chkCreate_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); //form 4`
- `dword chkStart_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold); //form 5`
- `dword chkStart_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, char* callback); //form 6`
- `dword chkStart_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId); //form 7`
- `dword chkStart_ADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback); //form 8`

## Constructor

- `TestCheck::CreateADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold);`
- `TestCheck::CreateADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::CreateADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::CreateADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold);`
- `TestCheck::StartADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId);`
- `TestCheck::StartADASGroundTruthObjectsDistanceViolation (dword underOver, float threshold, int64 laneId, int64 movingObjectId, char* callback);`

## Check Name

[ADAS Ground Truth Objects Distance Observation](../../../TestCommands/CheckDescriptions/CDADASGroundTruthObjectsDistanceObservation.md)

## Description

Observes the distance of the Moving Objects to the EgoVehicle. The check fires an event if the distance conditions passed as arguments are fulfilled.

## Parameters

- **overUnder**: Specifies if the distance violation is over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum distance. The distance is specified in meter.
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

```cpp
enum OverUnder
{
    kUnder = 0,
    kOver = 1
};

dword checkId1, checkId2;
checkId1 = chkStart_ADASGroundTruthObjectsDistanceViolation(kUnder, 10.0); // distance under 10m to EgoVehicle of any Moving Object will trigger the check
checkId2 = chkStart_ADASGroundTruthObjectsDistanceViolation(kOver, 500.0, 2, 100); // distance over 500m from EgoVehicle to Moving Object with ID 100 on lane with ID 2 will trigger the check

TestAddCondition(checkId1);
TestAddCondition(checkId2);
// sequence of different actions and waiting conditions
TestWaitForTimeout(3000);
TestRemoveCondition(checkId1);
TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
