[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILACKmsg.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ACK, VTIL_ACKMsg**

# VTIL_ACK, VTIL_ACKMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ACK(dword duration ); // form 1`
- `long VTIL_ACK(dbNode vt, dword duration); // form 2`
- `long VTIL_ACKMsg(dword objectId, dword keyActivationCode); // form 3`
- `long VTIL_ACKMsg (dbNode vt, dword objectId, dword keyActivationCode); // form 4`

## Description

Simulates the press of the ACK means of the Virtual Terminal. As a result, the **Soft Key Activation** message is immediately sent to the active Working Set with key activation code = **pressed**, then every 200 ms with the key activation code = **still held** and after the duration with the key activation code = **released**.

The **VTIL_ACKMsg** methods only send the Soft Key Activation message to the active Working Set (without triggering any event in the Virtual Terminal). In the sent **Soft Key Activation** messages the object ID of the **Key** object is always **0xFFFF** and the key number is always **0**.

## Parameters

- **vt**: VT simulation node to apply the function.
- **objectId**: Object ID of visible Data Mask or Alarm Mask.
- **duration**: Time while the ACK is held [ms]. If duration is < 200 ms then the commands **Key has been pressed** and **Key has been released** are sent. Else the command **Key is still pressed** is sent too.
- **keyActivationCode**:
  - 0: Key has been released (state change)
  - 1: Key has been pressed (state change)
  - 2: Key is still pressed
  - 3: Key press aborted

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
