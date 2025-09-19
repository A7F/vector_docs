[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILStartTask.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_StartTask**

# TCIL_StartTask

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long TCIL_StartTask(); // form 1`
- `long TCIL_StartTask(dbNode tc); // form 2`

## Description

This function starts a task.

## Parameters

- **tc**: Task Controller simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 2

```plaintext
long result;
result = TCIL_StartTask(TC);
switch (result)
{
  case 0: TestStepPass(); break;
  case -2202: TestStepFail("Function is not available in passive mode of the TC IL!"); break;
  case -2207: TestStepFail("Cannot start task in the current state of the TC IL!"); break;
  default: TestStepFail("Unexpected error"); break;
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
