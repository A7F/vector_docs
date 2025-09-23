[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetWSMAAddr.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_GetWSMAddr

# Iso11783IL_GetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783IL_GetWSMAddr();
```

## Description

This function returns the address of the Working Set Master, which is assigned to this ECU.

## Parameters

—

## Return Values

Address of the Working Set Master for this ECU or the Null-Address (0xFE).

## Example

```plaintext
addr = Iso11783IL_GetWSMAddr();
```
