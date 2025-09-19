[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestResetNodeSignalValues.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestResetNodeSignalValues

# TestResetNodeSignalValues

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestResetNodeSignalValues (dbNode aNode);
```

## Description

Resets all tx-signals of the given node to their initial value. The sending of the messages depends on the messages send type.

The reset-function does not contain a waiting time which guarantees that all signals are sent out on the bus. If a waiting time is desired, the [TestWaitForTimeout](CAPLfunctionTestWaitForTimeout.md) function has additionally been executed.

**Note**: Dependent on the used parameter type, the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aNode**: Node which tx-signals should be reset.

## Return Values

- **0**: No error
- **-1**: General error

## Example

```c
// check reaction of signal "LockState" after crash
$CrashDetected = 1;
TestWaitForTimeout(100);
if ($LockState !=  Unlocked)
    TestStepFail("Doors are locked after crash is detected!");

// reset test signals of node "SUT"
TestResetNodeSignalValues(SUT);
TestWaitForTimeout(200);
```

[TestResetEnvVarValue](CAPLfunctionTestResetEnvVarValue.md) • [TestResetNamespaceSysVarValues](CAPLfunctionTestResetNamespaceSysVarValues.md) • [TestResetSignalValue](CAPLfunctionTestResetSignalValue.md) • [TestResetSysVarValue](CAPLfunctionTestResetSysVarValue.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
