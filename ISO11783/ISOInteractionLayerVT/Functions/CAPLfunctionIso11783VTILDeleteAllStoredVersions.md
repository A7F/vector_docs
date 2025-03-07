[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILDeleteAllStoredVersions.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_DeleteAllStoredVersions

# VTIL_DeleteAllStoredVersions

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_DeleteAllStoredVersions();` // form 1
- `long VTIL_DeleteAllStoredVersions(dbNode vt);` // form 2

## Description

Deletes all object pool versions which are stored by the Virtual Terminal IL.

For more information see chapter **[Save Object Pools in VT Storage](../../../../Shared/ISO11783/ISO11783ILVT.md)**.

## Parameters

- **vt**: VT simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—