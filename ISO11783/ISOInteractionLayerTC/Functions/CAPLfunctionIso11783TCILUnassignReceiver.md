[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILUnassignReceiver.md)

# TCIL_UnassignReceiver

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_UnassignReceiver

### Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_UnassignReceiver(dword ddi, dbNode user, dword elementNumberUser, dbNode source) // form 1`
- `long TCIL_UnassignReceiver(dword ddi, dword addressUser, dword elementNumberUser, dword addressSource) // form 2`
- `long TCIL_UnassignReceiver(dbNode tc, dword ddi, dbNode user, dword elementNumberUser, dbNode source) // form 3`
- `long TCIL_UnassignReceiver(dbNode tc, dword ddi, dword addressUser, dword elementNumberUser, dword addressSource) // form 4`

## Description

The functions send an **Unassign Receiver** message to the **setpoint value user** device.

## Parameters

- **ddi**: This DDI and the element number specify the setpoint value user.
- **user**: Peer control capable device which acts as a setpoint value user.
- **addressUser**: Address of the peer control capable device which acts as a setpoint value user.
- **elementNumberUser**: The combination of this element number and the DDI shall no longer receive data from the setpoint value source.
- **source**: Peer control capable device which acts as a setpoint value source.
- **addressSource**: Address of the peer control capable device which acts as a setpoint value source.
- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—