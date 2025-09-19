[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportCreateRecordingGroup.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportCreateRecordingGroup

# TestReportCreateRecordingGroup

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function can only be used in test units with report configured to use Test Report Viewer format.

## Function Syntax

```
dword testReportCreateRecordingGroup(char name[]);
```

## Description

Creates a recording group with the given name. Afterwards a desired set of symbols can be added to the group.

## Parameters

- **name**: The name of the recording group.

## Return Values

- **> 0**: The handle of the created recording group.

## Example

```plaintext
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

[TestReportAddToRecordingGroup](CAPLfunctionTestReportAddToRecordingGroup.md) • [TestReportStartRecordingGroup](CAPLfunctionTestReportStartRecordingGroup.md) • [TestReportStopRecordingGroup](CAPLfunctionTestReportStopRecordingGroup.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
