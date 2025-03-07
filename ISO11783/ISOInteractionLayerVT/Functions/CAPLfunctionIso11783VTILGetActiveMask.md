[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetActiveMask.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetActiveMask**

# VTIL_GetActiveMask

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetActiveMask(dword & maskId);` // form 1
- `long VTIL_GetActiveMask(dbNode vt, dword & maskId);` // form 2

## Description

Returns object ID of the active Data or Alarm Mask.

## Parameters

- **vt**: VT simulation node to apply the function
- **maskId**: Returns object ID of the active data- or alarm mask

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example for test node

```c
long result;
dword maskId;
result = VTIL_GetActiveMask(VT, maskId);
switch (result)
{
  case 0:
    write("ID of current mask is %u", maskId);
    TestStepPass();
    break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2106: TestStepFail("Currently there is no active Data or Alarm mask!"); break;
  default:    TestStepFail("Unexpected error!"); break;
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)