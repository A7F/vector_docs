[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILControlStart.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ControlStart

# VTIL_ControlStart

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ControlStart(); // form 1`
- `long VTIL_ControlStart(byte address); // form 2`
- `long VTIL_ControlStart(dbNode vt); // form 3`
- `long VTIL_ControlStart(dbNode vt, byte address); // form 4`

## Description

The Virtual Terminal starts Address Claiming (if NMT is activated). If the Address Claiming was successful, cyclic messages are sent.

## Parameters

- **vt**: VT simulation node to apply the function
- **address**: Source address of the node (optional)

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See [VTIL_ControlStop](CAPLfunctionIso11783VTILControlStop.md)
