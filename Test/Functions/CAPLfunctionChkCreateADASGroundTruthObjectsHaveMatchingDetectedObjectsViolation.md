[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionChkCreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation.md)

**CAPL Functions** » **Test Service Library** » **Checks** » ChkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation, ChkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation

# ChkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation, ChkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `dword chkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU); //form 1`
- `dword chkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, char* callback); //form 2`
- `dword chkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId); //form 3`
- `dword chkCreate_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId, char* callback); //form 4`
- `dword chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU); //form 5`
- `dword chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, char* callback); //form 6`
- `dword chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId); //form 7`
- `dword chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId, char* callback); //form 8`

## Constructor

- `TestCheck::CreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU);`
- `TestCheck::CreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, char* callback);`
- `TestCheck::Create_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId);`
- `TestCheck::CreateADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU);`
- `TestCheck::StartADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, char* callback);`
- `TestCheck::StartADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId);`
- `TestCheck::StartADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (float minIoU, int64 movingObjectId, char* callback);`

## Description

Observes if Moving Objects have matching Detected Moving Objects. The check fires an event if the specified Moving Objects don’t have corresponding Detected Moving Objects.

## Parameters

- **minIoU**  
  The minimum required Intersection over Union (IoU) between the Detected Moving Object and the Moving Object. IoU is defined as the intersection volume between the two objects divided by the volume of the union of both objects.

- **movingObjectId**  
  GroundTruthId of the Moving Object. Only this Moving Object will be checked. If the value -1 is given or no movingObjectId is specified, all Moving Objects will be checked.

- **callback**  
  This parameter is optional. Name of the callback which is called when the check fails. Signature: `void Callback(dword checkId)` or `void Callback(TestCheck check)`.

## Return Values

- **0**  
  Check could not be created and must not be referenced

- **> 0**  
  Check was created successfully and may be referenced using the returned (handle-) value.

## Example

```plaintext
dword checkId1, checkId2;

checkId1 = chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (0.5); // minimum IoU is 50%, all Moving Object are checked

checkId2 = chkStart_ADASGroundTruthObjectsHaveMatchingDetectedObjectsViolation (0.5, 100); // minimum IoU is 50%, only Moving Object with Id 100 is checked

TestAddCondition(checkId1);

TestAddCondition(checkId2);

// sequence of different actions and waiting conditions

TestWaitForTimeout(3000);

TestRemoveCondition(checkId1);

TestRemoveCondition(checkId2);
```

[Functions to Configure Checks](../CAPLfunctionsTSLConfigurationFunctions.md) • [Commands to Control Checks](../CAPLfunctionsTSLCheckControlCommands.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
