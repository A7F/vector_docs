[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILControlInit.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_ControlInit**

# FSIL_ControlInit

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_ControlInit(); // form 1
long FSIL_ControlInit(dbNode fs); // form 2
```

## Description

Suppress the auto-start function of the IL.

This function can only be used in **on preStart**, to suppress the auto-start function of the IL.

## Parameters

- **fs**: FS simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example form 1**

```plaintext
on preStart
{
    FSIL_ControlInit();
}
```
