[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILGetAddress.md)

**CAPL Functions** » **J1939** » **GB/T 27930 IL** » **GBT27930IL_GetAddress**

# GBT27930IL_GetAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_GetAddress();` // form 1
- `long GBT27930IL_GetAddress(dbNode node);` // form 2

## Description

Returns the address that is used by the GBT27930 IL.

## Parameters

- **node**: Simulation node to apply the function

## Return Values

- **≥ 0**: address of the GBT27930 IL
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 'a'
{
  LONG addr;
  addr = GBT27930IL_GetAddress();
}
```
