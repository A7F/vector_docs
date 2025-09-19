[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysGetVariableMemberPhys.md)

# sysGetVariableMemberPhys

[CAPL Functions](../../CAPLfunctions.md) » [System Variables](../CAPLfunctionsSystemVariablesOverview.md) » sysGetVariableMemberPhys

Valid for: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long sysGetVariableMemberPhys(char namespace[], char variableAndMemberName[], double& value); // form 1
long sysGetVariableMemberPhys(SysVarMemberName, double& value); // form 2
```

## Description

Retrieves the physical value of a specific element of a variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md).

**Note**  
[Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md)

## Parameters

- **namespace**: Name of the namespace.
- **variableAndMemberName**: Name of the variable and the element of the struct/array.
- **SysVarName**: Name of the fully qualified name of the system variable element, including all namespaces, separated by "::". The name must be preceded by "sysVarMember::".
- **value**: Receives the current physical value of the element.

## Return Values

- **0**: no error, function successful
- **2**: variable or element were not found
- **4**: the element has no suitable type for the function

## Example

```plaintext
double val;
sysGetVariableMemberPhys(sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0], val);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
