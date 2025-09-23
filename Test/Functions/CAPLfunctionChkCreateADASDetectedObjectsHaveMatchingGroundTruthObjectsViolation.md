# ChkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation, ChkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `dword chkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU); //form 1`
- `dword chkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, char* callback); //form 2`
- `dword chkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId); //form 3`
- `dword chkCreate_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId, char* callback); //form 4`
- `dword chkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU); //form 5`
- `dword chkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, char* callback); //form 6`
- `dword chkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId); //form 7`
- `dword chkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId, char* callback); //form 8`

## Constructor

- `TestCheck::CreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU);`
- `TestCheck::CreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, char* callback);`
- `TestCheck::CreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId);`
- `TestCheck::CreateADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId, char* callback);`
- `TestCheck::StartADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU);`
- `TestCheck::StartADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, char* callback);`
- `TestCheck::StartADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId);`
- `TestCheck::StartADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (float minIoU, int64 trackingId, char* callback);`

## Description

Observes if Detected Moving Objects have matching Moving Objects. The check fires an event if the specified Detected Moving Objects don’t have corresponding Moving Objects.

## Parameters

- **minIoU**: The minimum required Intersection over Union (IoU) between the Detected Moving Object and the Moving Object. IoU is defined as the intersection volume between the two objects divided by the volume of the union of both objects.

- **trackingId**: TrackingId of the Detected Moving Object. Only this Detected Moving Object will be checked. If the value -1 is given or no trackingId is specified, all Detected Moving Objects will be checked.

- **callback**: This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback(dword checkId)` or `void Callback(TestCheck check)`.

## Return Values

- **0**: Check could not be created and must not be referenced
- **\> 0**: Check was created successfully and may be referenced using the returned (handle-) value.

## Example

```c
dword checkId1, checkId2;

checkId1 = chkStart_DASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (0.5); // minimum IoU is 50%, all Detected Moving Object are checked

checkId2 = chkStart_ADASDetectedObjectsHaveMatchingGroundTruthObjectsViolation (0.5, 100); // minimum IoU is 50%, only Detected Moving Object with Id 100 is checked

TestAddCondition(checkId1);

TestAddCondition(checkId2);

// sequence of different actions and waiting conditions

TestWaitForTimeout(3000);

TestRemoveCondition(checkId1);

TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)
