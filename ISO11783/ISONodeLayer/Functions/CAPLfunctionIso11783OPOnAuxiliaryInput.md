[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISONodeLayer/Functions/CAPLfunctionIso11783OPOnAuxiliaryInput.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Node Layer](../CAPLfunctionsISONLOverview.md) » Iso11783OPOnAuxiliaryInput

# Iso11783OPOnAuxiliaryInput (Callback)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783OPOnAuxiliaryInput(dword ecuHandle, dword objectID, dword value1, dword value2);
```

## Description

The function is called by the node layer, if an **Auxiliary Input Status** is received and a **Auxiliary Function** in the object pool is assigned.

## Parameters

- **ecuHandle**: Handle of the ECU
- **objectID**: Object identifier of the auxiliary function object
- **value1**: Value 1
- **value2**: Value 2

## Return Values

—

## Example

```c
void Iso11783OPOnAuxiliaryInput(dword handle, dword objectID, dword value1, dword value2) {
}
```
