[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASDetectedObjectsTimeToCollisionViolation.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Service Library](../CAPLfunctionsTSLOverview.md) » [Checks](../CAPLfunctionsTSLCheckOverview.md) » ChkCreate_ADASDetectedObjectsTimeToCollisionViolation, ChkStart_ADASDetectedObjectsTimeToCollisionViolation

# ChkCreate_ADASDetectedObjectsTimeToCollisionViolation, ChkStart_ADASDetectedObjectsTimeToCollisionViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword chkCreate_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold); //form 1`
- `dword chkCreate_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback); //form 2`
- `dword chkCreate_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId); //form 3`
- `dword chkCreate_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId, char* callback); //form 4`
- `dword chkStart_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold); //form 5`
- `dword chkStart_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback); //form 6`
- `dword chkStart_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId); //form 7`
- `dword chkStart_ADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId, char* callback); //form 8`

## Constructor

- `TestCheck::CreateADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold);`
- `TestCheck::CreateADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::CreateADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId);`
- `TestCheck::CreateADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId, char* callback);`
- `TestCheck::StartADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold);`
- `TestCheck::StartADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, char* callback);`
- `TestCheck::StartADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId);`
- `TestCheck::StartADASDetectedObjectsTimeToCollisionViolation (dword underOver, float threshold, int64 trackingId, char* callback);`

## Check Name

[ADAS Detected Objects Time To Collision Observation (TTC)](../../../TestCommands/CheckDescriptions/CDADASDetObjTimeToCollisionObservation.md)

## Description

Observes the Time To Collision (TTC) to the Detected Moving Objects. The check fires an event if the TTC conditions passed as arguments are fulfilled.

## Parameters

- **overUnder**: Specifies if the TTC is over or under the specified value.
- **threshold**: Specified value that determines the maximum or minimum TTC. The distance is specified in meter.
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

dword checkId1, checkId2;
checkId1 = chkStart_ADASDetectedObjectsTimeToCollisionViolation (kUnder, 1.0); // TTC under 1s to any Moving Object will trigger the check
checkId2 = chkStart_ADASDetectedObjectsTimeToCollisionViolation (kOver, 5.0, 2, 100); // TTC over 5s to Detected Moving Object with ID 100 will trigger the check

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
