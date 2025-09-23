[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SystemVariables/Functions/CAPLfunctionSysSetVariableMemberPhys.md)

**CAPL Functions** » **System Variables** » **sysSetVariableMemberPhys**

# sysSetVariableMemberPhys

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long sysSetVariableMemberPhys(char namespace[], char variableAndMemberName[], double value); // form 1`
- `long sysSetVariableMemberPhys(SysVarMemberName, double value); // form 2`

## Description

Sets the physical value of a specific element of a variable of type [struct or generic array](../../../Shared/SystemVariables/SysVar.md).

**Note**: [Direct access to values from system variables](../../../Shared/CAPL/SignalOrientedProgramming/SOPAccessSystemVariable.md)

## Parameters

- **namespace**: Name of the namespace.
- **variableAndMemberName**: Name of the variable and the element of the struct/array.
- **SysVarName**: Name of the fully qualified name of the system variable element, including all namespaces, separated by "::". The name must be preceded by "sysVarMember::".
- **value**: Sets the new physical value of the element.

## Return Values

- **0**: no error, function successful
- **2**: variable or element were not found
- **3**: no writing right for the variable available
- **4**: the element has no suitable type for the function

## Example

```c
sysSetVariableMemberPhys(sysvarMember::SomeNamespace::SomeStructVariable.SomeArrayMember[0], 1.2);
```
