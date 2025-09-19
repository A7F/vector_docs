[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILAssignTransmitter.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_AssignTransmitter

# TCIL_AssignTransmitter

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_AssignTransmitter(dword ddi, dbNode user, dword elementNumberUser, dbNode source, dword elementNumberSource) // form 1`
- `long TCIL_AssignTransmitter(dword ddi, dword addressUser, dword elementNumberUser, dword addressSource, dword elementNumberSource) // form 2`
- `long TCIL_AssignTransmitter(dbNode tc, dword ddi, dbNode user, dword elementNumberUser, dbNode source, dword elementNumberSource) // form 3`
- `long TCIL_AssignTransmitter(dbNode tc, dword ddi, dword addressUser, dword elementNumberUser, dword addressSource, dword elementNumberSource) // form 4`

## Description

The functions send an **Assign Transmitter** message to the **setpoint value source** device.

## Parameters

- **ddi**: This DDI and the element number specify the setpoint value user.
- **user**: Peer control capable device which acts as a setpoint value user.
- **addressUser**: Address of the peer control capable device which acts as a setpoint value user.
- **elementNumberUser**: The combination of this element number and the DDI receives data from the setpoint value source.
- **source**: Peer control capable device which acts as a setpoint value source.
- **addressSource**: Address of the peer control capable device which acts as a setpoint value source.
- **elementNumberSource**: The value of the process variable specified by combination of this element number and the DDI has to be sent to the setpoint value user.
- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
