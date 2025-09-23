[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILSetNodeProperty.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_SetNodeProperty

# VTIL_SetNodeProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_SetNodeProperty( char propertyName[], long propertyValue);` // form 1
- `long VTIL_SetNodeProperty( dbNode vt, char propertyName[], long propertyValue);` // form 2
- `long VTIL_SetNodeProperty( char propertyName[], char propertyValue[]);` // form 3
- `long VTIL_SetNodeProperty( dbNode vt, char propertyName[], char propertyValue[]);` // form 4

## Description

Changes an internal property of the node.

## Parameters

- **vt**: VT simulation node to apply the function
- **propertyName**: Name of the property (see [Properties of VT IL](../CAPLfunctionsISOILVTProperties.md) and [Network Properties of VT IL](../CAPLfunctionsISOILVTNetworkProperties.md))
- **propertyValue**: New value for the property

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
void SetNodeProperties()
{
  // Set language to English
  VTIL_SetNodeProperty(VT, "languageCode", 0x656E);
  // Object Pools have to be stored in the subdirectory "OP_VT1"
  VTIL_SetNodeProperty(VT, "locationOfStoredObjectPools", "OP_VT1");
}
```
