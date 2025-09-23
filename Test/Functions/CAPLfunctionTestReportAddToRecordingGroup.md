# TestReportAddToRecordingGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

- `testReportAddToRecordingGroup(dword groupHandle, signal aSignal);`
- `testReportAddToRecordingGroup(dword groupHandle, signal aSignal, char alias[]);`
- `testReportAddToRecordingGroup(dword groupHandle, sysvar aSysVar);`
- `testReportAddToRecordingGroup(dword groupHandle, sysvar aSysVar, char alias[]);`
- `testReportAddToRecordingGroup(dword groupHandle, valueHandle* aDOMember);`
- `testReportAddToRecordingGroup(dword groupHandle, valueHandle* aDOMember, char alias[]);`

## Description

Adds a symbol to the given recording group in the test report. Optionally, an alias for the symbol to show in the test report instead of the symbol name can be set.

All contained symbols in a recording group will be recorded when the recording of the group is started. Once the recording of a group is started, the set of symbols in the group cannot be changed anymore.

## Parameters

- **groupHandle**: The handle of the recording group.
- **aSignal**: The signal to add to the recording group.
- **aSysVar**: The system variable to add to the recording group.
- **aDOMember**: The distributed object member to add to the recording group.
- **alias**: The alias to show instead of the symbol name.

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

[TestReportCreateRecordingGroup](CAPLfunctionTestReportCreateRecordingGroup.md) • [TestReportStartRecordingGroup](CAPLfunctionTestReportStartRecordingGroup.md) • [TestReportStopRecordingGroup](CAPLfunctionTestReportStopRecordingGroup.md)
