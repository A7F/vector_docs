[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILEditStringValue.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » VTIL_EditStringValue, VTIL_ChangeStringValueMsg

# VTIL_EditStringValue, VTIL_ChangeStringValueMsg

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long VTIL_EditStringValue(dword objectId, char value[], dword duration); // form 1`
- `long VTIL_EditStringValue(dword objectId, char value[], dword duration, dword option); // form 2`
- `long VTIL_EditStringValue(dbNode vt, dword objectId, char value[], dword duration); // form 3`
- `long VTIL_EditStringValue(dbNode vt, dword objectId, char value[], dword duration, dword option); // form 4`
- `long VTIL_ChangeStringValueMsg(dword objectId, char value[]); // form 5`
- `long VTIL_ChangeStringValueMsg(dbNode vt, dword objectId, char value[]); // form 6`

## Description

Editing of an Input String object.

The VTIL_EditStringValue methods simulate the selection, opening, value modification and closing of the Input String object. The corresponding VT messages are sent. If the object is already selected or opened for input, then the steps **Select**, **Open** and **Close** are skipped.

The VTIL_ChangeStringValueMsg methods send only the VT Change String Value message (without influencing any button or input object and without triggering any event in the Virtual Terminal).

## Parameters

- **vt**: VT simulation node to apply the function
- **objectId**: Input object ID
- **value**: New string value
- **duration [ms]**: After this duration the edit process ends
- **option**:
  - 0: No additional option
  - 1: Edit object even it is not part of the active Data/Alarm Mask

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3 and 6

```plaintext
long result;
result = VTIL_EditStringValue (VT, 301, "text", 2000);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2106: TestStepFail("Currently there is no active Data or Alarm mask!"); break;
  case -2115: TestStepFail("VT works in passiv mode therefore you cannot select objects!"); break;
  case -2117: TestStepFail("Failed to open object for editing!"); break;
  case -2118: TestStepFail("Object is no Input String object!"); break;
  case -2120: TestStepFail("Failed to edit object because it is disabled!"); break;
  case -2121: TestStepFail("Button is not available in the current context!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```
