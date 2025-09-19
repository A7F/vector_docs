[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsDistanceViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_ADASDetectedObjectsDistanceViolation, ChkStart_ADASDetectedObjectsDistanceViolation

# ChkCreate_ADASDetectedObjectsDistanceViolation, ChkStart_ADASDetectedObjectsDistanceViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword chkCreate_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold); //form 1`
- `dword chkCreate_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, char* callback); //form 2`
- `dword chkCreate_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId); //form 3`
- `dword chkCreate_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId, char* callback); //form 4`
- `dword chkStart_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold); //form 5`
- `dword chkStart_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, char* callback); //form 6`
- `dword chkStart_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId); //form 7`
- `dword chkStart_ADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId, char* callback); //form 8`

## Constructor

[TestCheck::CreateADASDetectedObjectsDistanceViolation (dword underOver, float threshold);](../../../Shared/CAPL/General/ClassesAndObjects.md)

- `TestCheck::CreateADASDetectedObjectsDistanceViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::CreateADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId);`
- `TestCheck::CreateADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId, char* callback);`
- `TestCheck::StartADASDetectedObjectsDistanceViolation (dword underOver, float threshold);`
- `TestCheck::StartADASDetectedObjectsDistanceViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::StartADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId);`
- `TestCheck::StartADASDetectedObjectsDistanceViolation (dword underOver, float threshold, int64 trackingId, char* callback);`

## Check Name

[ADAS Detected Objects Distance Observation](../../../TestCommands/CheckDescriptions/CDADASDetObjDistanceObservation.md)

## Description

Observes the distance of the Detected Moving Objects. The check fires an event if the distance conditions passed as arguments are fulfilled.

## Parameters

- **overUnder**: Specifies if the distance violation is over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum distance. The distance is specified in meter.
- **trackingId**: TrackingId of the Detected Moving Object. Only the distance to this Detected Moving Object will be checked. If the value **-1** is given, all Detected Moving Objects will be checked.
- **callback**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback( dword checkId)` or `void Callback( TestCheck check)`.

## Return Values

- **0**: Check could not be created and must not be referenced
- **> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Possible Errors

- CAPL callback does not exist.

## Example

```c
enum OverUnder
  {
    kUnder = 0,
    kOver = 1
  };

dword  checkId1, checkId2;
checkId1 = chkStart_ADASDetectedObjectsDistanceViolation kUnder, 10.0); // distance under 10m to any Detected Moving Object will trigger the check
checkId2 = chkStart_ADASDetectedObjectsDistanceViolation (kOver, 500.0, 2, 100); // distance over 500m from to Detected Moving Object with ID 100 will trigger the check

TestAddCondition(checkId1);
TestAddCondition(checkId2);
// sequence of different actions and waiting conditions
TestWaitForTimeout(3000);
TestRemoveCondition(checkId1);
TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
