[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILPressISB.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_PressISB

# VTIL_PressISB

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_PressISB(dword duration); // form 1`
- `long VTIL_PressISB(dbNode vt, dword duration); // form 2`

## Description

The **VTIL_PressButton** methods simulate pressing the ISOBUS Shortcut Button **[ISB]** of the Virtual Terminal and releasing it after the duration. As a result, the **All Implements Stop Operations Switch State Message** is sent with the value **Stop implement operations** until the ISB is released.

Every time the function is called, the **Number of transitions from Permit to Stop** is incremented.

## Parameters

- **vt**: VT simulation node to apply the function.
- **duration**: Time while the ISB is pressed [ms].

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example for test node

```plaintext
long result;
result = VTIL_PressISB(VT,  300);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2115: TestStepFail("VT works in passive mode therefore you cannot press the ISB button!"); break;
  case -2121: TestStepFail("ISB Button is not available because property ‚isbServer‘ is not set!"); break;
  default: TestStepFail("Unexpected error"); break;
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
