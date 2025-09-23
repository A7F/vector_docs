[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPChangeSoftKeyMask.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPChangeSoftKeyMask

# Iso11783IL_OPChangeSoftKeyMask

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPChangeSoftKeyMask( dword maskID, dword softKeyMaskID ); // form 1`
- `long Iso11783IL_OPChangeSoftKeyMask( dword maskType, dword maskID, dword softKeyMaskID ); // form 2`
- `long Iso11783IL_OPChangeSoftKeyMask( dbNode implement, dword maskType, dword maskID, dword softKeyMaskID ); // form 3`

## Description

The function changes the soft key mask of a data mask. A **Change Soft Key Mask** command is sent to the Virtual Terminal.

If parameter **maskType** is not used the mask type is determined by the mask object.

## Parameters

- **maskID**: object ID of the data mask
- **softkeyMaskID**: object ID of the data mask
- **maskType**: type of mask
  - 1: data mask
  - 2: alarm mask
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPChangeSoftKeyMask( 1000, 1050 );
```
