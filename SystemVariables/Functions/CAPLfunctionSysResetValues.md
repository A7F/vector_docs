[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysResetValues.md)

**CAPL Functions** » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysResetValues

# sysResetValues

**Valid for**: [CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysResetValues(char namespace[]);
```

## Description

Resets all system variables in a namespace to their initial values. This recursively includes all variables in sub-namespaces.

## Parameters

- **namespace**: Name of the namespace.

## Return Values

- **0**: Success
- **1**: At least one variable in the namespace has no initial value assigned
- **-1**: The namespace doesn’t exist

## Example

—

[sysResetValue](CAPLfunctionSysResetValue.md) • [testResetNamespaceSysVarValues](../../Test/Functions/CAPLfunctionTestResetNamespaceSysVarValues.md) • [resetDistObjValues](../../DistributedObjects/Functions/CAPLfunctionResetDistObjValues.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)