[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILESC.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ESC, VTIL_ESCMsg**

# VTIL_ESC, VTIL_ESCMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ESC();` // form 1
- `long VTIL_ESC(dbNode vt);` // form 2
- `long VTIL_ESCMsg(dbNode workingSetMaster, dword objectId, dword errorCodes);` // form 3
- `long VTIL_ESCMsg (dbNode vt, dbNode workingSetMaster, dword objectId, dword errorCodes);` // form 4

## Description

The VTIL_ESC methods simulate the press of the ESC means of the Virtual Terminal. As a result, the VT ESC message with the Object ID, where input was aborted, is sent.

The VTIL_ESCMsg methods send the VT ESC message (without triggering any event in the Virtual Terminal).

## Parameters

- **vt**: VT simulation node to apply the function.
- **workingSetMaster**: Working Set Master which provides the object pool.
- **objectId**: Object ID where input was aborted.
- **errorCodes**:
  - bit 0 = 1: No input field is selected (this bit is only used when the VT has a permanent ESC means)
  - bit 1..3: Undefined, set to 0 recommended
  - bit 4 = 1: Any other error

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
