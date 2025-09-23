[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILControlStart.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ControlStart**

# TCIL_ControlStart

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ControlStart();` // form 1
- `long TCIL_ControlStart(byte address);` // form 2
- `long TCIL_ControlStart(dbNode tc);` // form 3
- `long TCIL_ControlStart(dbNode tc, byte address);` // form 4

## Description

The Task Controller starts Address Claiming (if NMT is activated). If the Address Claiming was successful, cyclic messages are sent.

## Parameters

- **tc**: TC simulation node to apply the function
- **address**: Source address of the node (optional)

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

See [TCIL_ControlStop](CAPLfunctionIso11783TCILControlStop.md)
