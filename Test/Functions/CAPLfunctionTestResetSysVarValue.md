# TestResetSysVarValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
long TestResetSysVarValue (sysvar aSysVar);
```

## Description

Resets the system variable to initial value. If no initial value is defined, the system variable is not set.

## Parameters

- **aSysVar**: System variable that should be reset.

## Return Values

- **0**: No error
- **-1**: General error

## Example

```c
// check reaction of signal "LockState" after crash
@sysvar::Error::SysVarCrashDetected = 1;
TestWaitForTimeout(100);
if ($LockState !=  Unlocked)
    TestStepFail("Doors are locked after crash is detected!");

// reset the crash system variable
TestResetSysVarValue(sysvar::Error::SysVarCrashDetected);
TestWaitForTimeout(200);
```

[TestResetEnvVarValue](CAPLfunctionTestResetEnvVarValue.md) • [TestResetNamespaceSysVarValues](CAPLfunctionTestResetNamespaceSysVarValues.md) • [TestResetNodeSignalValues](CAPLfunctionTestResetNodeSignalValues.md) • [TestResetSignalValue](CAPLfunctionTestResetSignalValue.md)
