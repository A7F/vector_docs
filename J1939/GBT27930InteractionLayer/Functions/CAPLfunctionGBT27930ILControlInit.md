[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILControlInit.md)

## GBT27930IL_ControlInit

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_ControlInit

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long GBT27930IL_ControlInit(); // form 1`
- `long GBT27930IL_ControlInit(dbNode node);  // form 2`

### Description

This function can only be used in **on preStart**, to suppress the auto-start function of the IL.

### Parameters

- **node**: Simulation node to apply the function

### Return Values

0 on success or [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

### Example

```plaintext
on preStart
{
    GBT27930IL_ControlInit();
}
```
