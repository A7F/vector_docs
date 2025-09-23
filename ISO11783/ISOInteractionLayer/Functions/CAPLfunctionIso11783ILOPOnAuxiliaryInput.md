[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPOnAuxiliaryInput.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPOnAuxiliaryInput

# Iso11783IL_OPOnAuxiliaryInput (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_OPOnAuxiliaryInput( dword objectID, dword value1, dword value2 );
```

## Description

The function is called by the node layer if an **Auxiliary Input Status** is received and an **Auxiliary Function** in the object pool is assigned.

## Parameters

- **objectID**: Object identifier of the auxiliary function object
- **value1**: Value 1
- **value2**: Value 2

## Return Values

—

## Example

```c
void Iso11783IL_OPOnAuxiliaryInput( dword objectID, dword value1, dword value2 )
{
}
```
