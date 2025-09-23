[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILRemoveAllDdops.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_RemoveAllDdops

# TCIL_RemoveAllDdops

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_RemoveAllDdops(); // form 1`
- `long TCIL_RemoveAllDdops(dbNode tc); // form 2`

## Description

Removes the device descriptor object pools of all Task Controller clients.

## Parameters

- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
long result;
result = TCIL_RemoveAllDdops( TC);
if (result < 0)
{
  TestStepFail("Failed to remove current DDOPs!");
}
```
