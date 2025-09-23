[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILGetAddress.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_GetAddress

# FSIL_GetAddress

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_GetAddress(); // form 1
long FSIL_GetAddress(dbNode fs); // form 2
```

## Description

Returns the address that is used by the FS IL.

## Parameters

- **fs**: FS simulation node to apply the function

## Return Values

- **≥ 0**: Address of the FS IL
- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 1

```plaintext
on key 'a'
{
  long addr;
  addr = FSIL_GetAddress();
}
```
