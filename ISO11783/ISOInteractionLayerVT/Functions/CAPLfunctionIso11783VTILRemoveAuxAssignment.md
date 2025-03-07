[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILRemoveAuxAssignment.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_RemoveAuxAssignment

# VTIL_RemoveAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_RemoveAuxAssignment(dbNode auxiliaryFunctionWSM, word auxiliaryFunctionId); // form 1`
- `long VTIL_RemoveAuxAssignment(dword addressAuxiliaryFunctionWSM, word auxiliaryFunctionId); // form 2`
- `long VTIL_RemoveAuxAssignment(dbNode vt, dbNode auxiliaryFunctionWSM, word auxiliaryFunctionId); // form 3`
- `long VTIL_RemoveAuxAssignment(dbNode vt, dword addressAuxiliaryFunctionWSM, word auxiliaryFunctionId); // form 4`

## Description

Removes an auxiliary assignment. As a result, the Auxiliary Assignment Type 2 command is sent to the Auxiliary Function Working Set Master. If there are no assignments for the Auxiliary Input, an Auxiliary Input Status Type 2 Enable command (Disable) is sent to the Auxiliary Input Working Set Master.

If the participants are using VT Version 0, 1, or 2, only an Auxiliary Assignment Type 1 command is sent to the Auxiliary Input.

## Parameters

- **vt**: VT simulation node to apply the function
- **auxiliaryFunctionWSM**: Working Set Master which provides the Auxiliary Function
- **addressAuxiliaryFunctionWSM**: Address of the Working Set Master which provides the Auxiliary Function
- **auxiliaryFunctionId**: Object ID of the Auxiliary Function. For value 0xFFFF, all assigned functions are removed

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
long result;
result = VTIL_RemoveAuxAssignment (VT, Loader, 1001);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2109: TestStepFail("The Working Set is not available!"); break;
  case -2118: TestStepFail("Object is not Auxiliary Function!"); break;
  case -2119: TestStepFail("The assignment failed!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)