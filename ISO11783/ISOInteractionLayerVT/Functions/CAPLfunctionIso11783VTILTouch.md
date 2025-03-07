[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILTouch.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_Touch, VTIL_PointingEventMsg**

# VTIL_Touch, VTIL_PointingEventMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_Touch(dword x, dword y, dword duration); // form 1`
- `long VTIL_Touch(dbNode vt, dword x, dword y, dword duration); // form 2`
- `long VTIL_PointingEventMsg(dword x, dword y, byte touchState); // form 3`
- `long VTIL_PointingEventMsg(dbNode vt, dword x, dword y, byte touchState); // form 4`
- `long VTIL_PointingEventMsg(dword x, dword y, byte touchState, dword parentMaskId); // form 5`
- `long VTIL_PointingEventMsg(dbNode vt, dword x, dword y, byte touchState, dword parentMaskId); // form 6`

## Description

Touches into the Data Mask.

The VTIL_Touch methods simulate a touch into the Data Mask and a release of the touch event after the duration. As a result, the Pointing Event Message is sent immediately with the touch state = **pressed**, then every 200 ms with the touch state = **Held** and after the duration with the touch state = **Released**.

If there is a button or input object at the specified position, the button or object is selected and pressed.

The VTIL_PointingEventMsg methods only send the Pointing Event Message (without influencing any button or input object and without triggering any event in the Virtual Terminal). You can use it to implement dragging operation.

## Parameters

- **vt**: VT simulation node to apply the function
- **x**: X Position in pixels relative to top left corner of Data Mask area
- **y**: Y Position in pixels relative to top left corner of Data Mask area
- **duration**: Time while the Data Mask is pressed [ms]. If duration is **0** then only the command **Pressed** is sent. Else the commands **Held** and **Released** are sent too.
- **touchState**:
  - 0: Released
  - 1: Pressed
  - 2: Held
  - 255: Used by VTs of version 3 or prior
- **parentMaskId**: Current Parent Mask Object ID (used by VTs of version 6 and later)

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

Example form 2, 4, 6

```plaintext
long result;
result = VTIL_Touch(VT, 1, 2, 500);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2115: TestStepFail("VT works in passive mode. Therefore you cannot touch it!"); break;
  default:    TestStepFail("Unexpected error"); break;
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)