[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILActivateWorkingSet.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ActivateWorkingSet**

# VTIL_ActivateWorkingSet

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ActivateWorkingSet(dbNode workingSetMaster); // form 1`
- `long VTIL_ActivateWorkingSet(byte workingSetMasterAddress); // form 2`
- `long VTIL_ActivateWorkingSet(dbNode vt, dbNode workingSetMaster); // form 3`
- `long VTIL_ActivateWorkingSet(dbNode vt, byte workingSetMasterAddress); // form 4`

## Description

Activates a corresponding Working Set in the Virtual Terminal: As a result, the VT Status message is sent with the source address of newly activated Working Set as well as its active Data/Alarm and Soft Key Mask.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master node
- **workingSetMasterAddress**: Address of the Working Set Master

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example for test node:

```plaintext
long result;
result = VTIL_ActivateWorkingSet(VT, Sprayer);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2109: TestStepFail ("Working Set 'Sprayer' is not available!"); break;
  case -2110: TestStepFail ("Failed to activate Working Set 'Sprayer'!"); break;
  default: TestStepFail ("Unexpected error"); break;
}
```
