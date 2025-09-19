[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestResetNamespaceSysVarValues.md)

## TestResetNamespaceSysVarValues

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestResetNamespaceSysVarValues

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

```plaintext
long TestResetNamespaceSysVarValues (char aNamespace[]);
```

### Description

Resets all system variables of the given namespace and all sub-namespaces to their initial value. If no initial value is defined for a system variable, the system variable is not set.

**aNamespace** is not allowed to be empty. If system variables without namespace should be reset, [TestResetSysVarValue](CAPLfunctionTestResetSysVarValue.md) has to be used.

### Parameters

- **aNamespace**: Namespace which system variables should be reset.

### Return Values

- **0**: No error
- **-1**: General error

### Example

```plaintext
// check the warning lights
@sysvar::Lights::SysVarWarningLights = 1;
TestWaitForTimeout(100);
if (@sysvar::Lights::SysVarWarningLightsDsp != 1)
    TestStepFail("Warning lights do not flash!");

// reset all "Lights" system variables
TestResetNamespaceSysVarValues("Lights");
TestWaitForTimeout(200);
```

### Related Links

- [TestResetEnvVarValue](CAPLfunctionTestResetEnvVarValue.md)
- [TestResetNodeSignalValues](CAPLfunctionTestResetNodeSignalValues.md)
- [TestResetSignalValue](CAPLfunctionTestResetSignalValue.md)
- [TestResetSysVarValue](CAPLfunctionTestResetSysVarValue.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
