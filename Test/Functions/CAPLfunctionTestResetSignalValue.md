[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestResetSignalValue.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestResetSignalValue

# TestResetSignalValue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestResetSignalValue (Signal aSignal); // form 1`
- `long TestResetSignalValue (ServiceSignal aSignal); // form 2`

## Description

Resets the signal to initial value. The sending depends on the message send type.

The reset-function does not contain a waiting time which guarantees that the signal is sent out on the bus. If a waiting time is desired, the [TestWaitForTimeout](CAPLfunctionTestWaitForTimeout.md) function has additionally been executed.

## Parameters

- **aSignal**: Signal that should be reset.

## Return Values

- **0**: No error
- **-1**: General error

## Example

```plaintext
// check reaction of signal "LockState" after crash
$CrashDetected = 1;
TestWaitForTimeout(100);
if ($LockState !=  Unlocked)
    TestStepFail("Doors are locked after crash is detected!");

// reset test signals
TestResetSignalValue(CrashDetected);
TestResetSignalValue(LockState);
TestWaitForTimeout(200);
```

[TestResetEnvVarValue](CAPLfunctionTestResetEnvVarValue.md) • [TestResetNamespaceSysVarValues](CAPLfunctionTestResetNamespaceSysVarValues.md) • [TestResetNodeSignalValues](CAPLfunctionTestResetNodeSignalValues.md) • [TestResetSysVarValue](CAPLfunctionTestResetSysVarValue.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
