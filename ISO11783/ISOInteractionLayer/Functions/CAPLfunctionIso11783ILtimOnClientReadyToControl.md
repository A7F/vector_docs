[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimOnClientReadyToControl.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMOnClientReadyToControl

# Iso11783IL_TIMOnClientReadyToControl

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void Iso11783IL_TIMOnClientReadyToControl(dword functionID, dword clientAddress)
```

## Description

This callback function is called if the TIM Client is ready to control a TIM function.

Within this callback you can call [Iso11783IL_TIMOperatorAcknowledge](CAPLfunctionIso11783ILtimOperatorAcknowledge.md) to acknowledge the request.

## Parameters

- **functionID**: Function ID of the TIM function.

- **clientAddress**: Address of TIM Client which is ready to control the function.

## Return Values

—

## Example

—
