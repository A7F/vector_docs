# TestReportStopRecordingGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

`testReportStopRecordingGroup(dword groupHandle);`

## Description

Stops the recording of all symbols contained in the recording group in the test report. If the recording group is not explicitly stopped it will be automatically stopped at the end of the test unit (or at the end of each execution cycle, respectively).

## Parameters

- **groupHandle**  
  The handle of the recording group to stop recording.

## Return Values

—

## Example

```c
DWORD groupHandle;

groupHandle = testReportCreateRecordingGroup("GroupName1");

testReportAddToRecordingGroup(groupHandle, sysvar::SVInt, "Sysvar_Alias1");
testReportAddToRecordingGroup(groupHandle, sysvarMember::SVStruct1.Member1, "Sysvar_Alias2");
testReportAddToRecordingGroup(groupHandle, comfort::VehicleMotion::CrashDetected);
testReportAddToRecordingGroup(groupHandle, comfort::CentralLockingSystemState::LockState);
testReportStartRecordingGroup(groupHandle);

// … do something

testReportStopRecordingGroup(groupHandle);
```

[TestReportAddToRecordingGroup](CAPLfunctionTestReportAddToRecordingGroup.md) • [TestReportCreateRecordingGroup](CAPLfunctionTestReportCreateRecordingGroup.md) • [TestReportStartRecordingGroup](CAPLfunctionTestReportStartRecordingGroup.md)
