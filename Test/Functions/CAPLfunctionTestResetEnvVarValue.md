[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestResetEnvVarValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestResetEnvVarValue

# TestResetEnvVarValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestResetEnvVarValue (dbEnvVar aEnvVar);
```

## Description

Resets the environment variable to initial value. If no initial value is available, the environment variable is set to 0 or "".

## Parameters

- **aEnvVar**: Environment variable that should be reset.

## Return Values

- **0**: No error
- **-1**: General error

## Example

```c
// check reaction of signal "LockState" after crash
@EnvErrorCrashDetected = 1;
TestWaitForTimeout(100);
if ($LockState !=  Unlocked)
    TestStepFail("Doors are locked after crash is detected!");

// reset the crash environment variable
TestResetEnvVarValue(EnvErrorCrashDetected);
TestWaitForTimeout(200);
```

[TestResetNamespaceSysVarValues](CAPLfunctionTestResetNamespaceSysVarValues.md) • [TestResetNodeSignalValues](CAPLfunctionTestResetNodeSignalValues.md) • [TestResetSignalValue](CAPLfunctionTestResetSignalValue.md) • [TestResetSysVarValue](CAPLfunctionTestResetSysVarValue.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)