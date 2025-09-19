[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILEditNumericValue.md)

**CAPL Functions » ISO11783 » Virtual Terminal Interaction Layer (VT IL) » VTIL_EditNumericValue, VTIL_ChangeNumericValueMsg**

# VTIL_EditNumericValue, VTIL_ChangeNumericValueMsg

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_EditNumericValue(dword objectId, double value, dword duration); // form 1`
- `long VTIL_EditNumericValue(dword objectId, double value, dword duration, dword option); // form 2`
- `long VTIL_EditNumericValue(dbNode vt, dword objectId, double value, dword duration); // form 3`
- `long VTIL_EditNumericValue(dbNode vt, dword objectId, double value, dword duration, dword option); // form 4`
- `long VTIL_ChangeNumericValueMsg(dword objectId, dword rawValue); // form 5`
- `long VTIL_ChangeNumericValueMsg(dbNode vt, dword objectId, dword rawValue); // form 6`

## Description

Editing of an Input Number object.

The VTIL_EditNumericValue methods simulate the selection, opening, value modification and closing of the Input Number or Input List object. The corresponding VT messages are sent.

If the object is already selected or opened for input, then the steps **Select**, **Open** and **Close** (and corresponding VT messages) are skipped.

The VTIL_ChangeNumericValueMsg methods send only the VT Change Numeric Value message (without influencing any button or input object and without triggering any event in the Virtual Terminal).

## Parameters

- **vt**: VT simulation node to apply the function
- **objectId**: Input object ID
- **value**: New numeric value which is displayed in the input field
- **rawValue**: This value is sent in the Change Numeric Value message
- **duration [ms]**: After this duration the edit process ends. If input object is already opened for input this parameter is ignored.
- **option**:
  - 0: No additional option
  - 1: Edit object even it is not part of the active Data/Alarm Mask

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

**Example 1: Form 3 and 6**

```c
// to simulate: operator enters value 12.0 into Input Number object with ID=240

long result;
result = VTIL_EditNumericValue(VT, 240, 12.0, 300);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2106: TestStepFail("Currently there is no active Data or Alarm mask!"); break;
  case -2115: TestStepFail("VT works in passive mode therefore you cannot edit objects!"); break;
  case -2117: TestStepFail("Failed to open Input object for editing!"); break;
  case -2118: TestStepFail("Object is neither Input Bool, Input Number nor Input List object!"); break;
  case -2120: TestStepFail("Object is disabled!"); break;
  case -2121: TestStepFail("Object is not available in the current context!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

**Example 2: Form 3 and 6**

Simulation of realtime editing:

```c
// to simulate: Realtime Editing of the numeric object with ID=220

VTIL_SelectInputObject(VT, 220, 1); // open for editing
TestWaitForTimeout(200);
VTIL_EditNumericValue(VT, 220, 1, 0); // type "1"
TestWaitForTimeout(500);
VTIL_EditNumericValue(VT, 220, 12, 0); // type additionally "2"
TestWaitForTimeout(600);
VTIL_EditNumericValue(VT, 220, 123, 0);  // type additionally "3"
TestWaitForTimeout(400);
VTIL_SelectInputObject(VT, 220, 0);    // finish editing
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
