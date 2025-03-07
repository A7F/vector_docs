[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetVTStatus.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » **VTIL_ResetVTStatus**

# VTIL_ResetVTStatus

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetVTStatus(); // form 1`
- `long VTIL_ResetVTStatus(dbNode vt); // form 2`

## Description

This function reverts changes made by [SetVTStatus](CAPLfunctionIso11783VTILSetVTStatus.md) and returns to the default behavior of the Virtual Terminal IL.

## Parameters

- **vt**: VT simulation node to apply the function

## Return Values

- **0**: Blocking of all messages has been stopped successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md).

## Example

Example form 2:

```c
if (VTIL_ResetVTStatus(VT) < 0)
{
  TestStepFail("Failed to reset VT Status message");
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)