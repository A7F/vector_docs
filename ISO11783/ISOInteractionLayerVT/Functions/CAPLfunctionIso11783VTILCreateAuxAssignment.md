[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILCreateAuxAssignment.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_CreateAuxAssignment**

# VTIL_CreateAuxAssignment

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_CreateAuxAssignment(dbNode auxiliaryFunctionWSM, dbNode auxiliaryInputWSM, word auxiliaryFunctionId, word auxiliaryInputId); // form 1`
- `long VTIL_CreateAuxAssignment(dword addressAuxiliaryFunctionWSM, dword addressAuxiliaryInputWSM, word auxiliaryFunctionId, word auxiliaryInputId); // form 2`
- `long VTIL_CreateAuxAssignment(dbNode vt, dbNode auxiliaryFunctionWSM, dbNode auxiliaryInputWSM, word auxiliaryFunctionId, word auxiliaryInputId); // form 3`
- `long VTIL_CreateAuxAssignment(dbNode vt, dword addressAuxiliaryFunctionWSM, dword addressAuxiliaryInputWSM, word auxiliaryFunctionId, word auxiliaryInputId); // form 4`

## Description

Assigns an Auxiliary Input to an Auxiliary Function.

As a result, the Auxiliary Input Status Type 2 Enable command is sent to the Auxiliary Input (if not already enabled) and the Auxiliary Assignment Type 2 command is sent to the Auxiliary Function Working Set Master.

If the participants are using VT Version 0, 1, or 2, only an Auxiliary Assignment Type 1 command is sent to the Auxiliary Input.

## Parameters

- **Vt**: VT simulation node to apply the function
- **auxiliaryFunctionWSM**: Working Set Master which provides the Auxiliary Function
- **addressAuxiliaryFunctionWSM**: Address of the Working Set Master which provides the Auxiliary Function
- **auxiliaryInputWSM**: Working Set Master which provides the Auxiliary Input
- **addressAuxiliaryInputWSM**: Address of the Working Set Master which provides the Auxiliary Input
- **auxiliaryFunctionId**: Object ID of the Auxiliary Function
- **auxiliaryInputId**: Object ID of the Auxiliary Input

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```c
long result;
result = VTIL_CreateAuxAssignment(VT, Loader, AuxInput, 1001, 1003);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2109: TestStepFail("A Working Set is not available!"); break;
  case -2118: TestStepFail("An object is not suitable!"); break;
  case -2119: TestStepFail("The assignment failed!"); break;
  default: TestStepFail("Unexpected error!"); break;
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
