[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILPressButton.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_PressButton, VTIL_ButtonActivationMsg

# VTIL_PressButton, VTIL_ButtonActivationMsg

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_PressButton(dword objectId, dword duration); // form 1`
- `long VTIL_PressButton(dword objectId, dword duration, dword maskId); // form 2`
- `long VTIL_PressButton(dbNode vt, dword objectId, dword duration); // form 3`
- `long VTIL_PressButton(dbNode vt, dword objectId, dword duration, dword maskId); // form 4`
- `long VTIL_ButtonActivationMsg(dword objectId, dword maskId, byte keyActivationCode, byte keyNumber); // form 5`
- `long VTIL_ButtonActivationMsg(dbNode vt, dword objectId, dword maskId, byte keyActivationCode, byte keyNumber); // form 6`

## Description

The VTIL_PressButton methods simulate the pressing of a Button and the releasing of it after the duration. As a result, the Button Activation Message is immediately sent with the key activation code = **pressed/latched**, then every 200 ms with the key activation code = **still held** and after the duration with the key activation code = **released/unlatched**.

For form 1 and 3 the button must be part of the active Data/Alarm/Window Mask. Otherwise, the function will return with an error code and no messages will be sent.

In contrast, forms 2, 4, 5 and 6 do not check whether the button belongs to the given Data/Alarm/Window mask or whether the button is active or visible.

The VTIL_ButtonActivationMsg methods send only the Button Activation Message (without triggering any event in the Virtual Terminal).

## Parameters

- **vt**: VT simulation node to apply the function
- **objectId**: Object ID of the Button
- **maskId**: Data/Alarm/Window mask ID that is to be sent with the corresponding Button Activation message (without checking if the button really belongs to the given Data/Alarm/Window mask or whether the button is active or visible).
- **duration**: Time while the Button is pressed [ms]. If duration is < 200 ms then only the commands **Button has been pressed or latched** and **Button has been unlatched or released** are sent. Else the command **Button is still held** is sent too.
- **keyActivationCode**:
  - 0: Button has been unlatched or released (state change)
  - 1: Button has been "pressed" or latched (state change)
  - 2: Button is still held (latchable buttons do not repeat)
  - 3: Button press aborted
- **keyNumber**: Overwrites the button key code of the Button object

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
long result;
result = VTIL_PressButton(VT, 3000, 400);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2115: TestStepFail("VT works in passive mode therefore you cannot press buttons!"); break;
  case -2120: TestStepFail("Button is currently disabled!"); break;
  case -2121: TestStepFail("Button is not available in the current context!"); break;
  default: TestStepFail("Unexpected error"); break;
}
```
