[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILGetDisplayedValue.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_GetDisplayedValue**

# VTIL_GetDisplayedValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_GetDisplayedValue(dbNode workingSetMaster, dword objectId, double & value); // form 1`
- `long VTIL_GetDisplayedValue(dword addressWorkingSetMaster, dword objectId, double & value); // form 2`
- `long VTIL_GetDisplayedValue(dbNode vt, dbNode workingSetMaster, dword objectId, double & value); // form 3`
- `long VTIL_GetDisplayedValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, double & value); // form 4`
- `long VTIL_GetDisplayedValue(dbNode workingSetMaster, dword objectId, char* buffer, dword bufferLength); // form 5: deprecated with 13`
- `long VTIL_GetDisplayedValue(dbNode vt, dbNode workingSetMaster, dword objectId, char* buffer, dword bufferLength); // form 6: deprecated with 13`
- `long VTIL_GetDisplayedValue(dbNode workingSetMaster, dword objectId, char* buffer); // form 7`
- `long VTIL_GetDisplayedValue(dword addressWorkingSetMaster, dword objectId, char* buffer); // form 8`
- `long VTIL_GetDisplayedValue(dbNode vt, dbNode workingSetMaster, dword objectId, char* buffer); // form 9`
- `long VTIL_GetDisplayedValue(dbNode vt, dword addressWorkingSetMaster, dword objectId, char* buffer); // form 10`

## Description

Returns the displayed value of an object.

If the object supports scaling/offset then the displayed value is

`displayed value = (value + offset) * scaling factor`

If the object uses a variable reference then the value of this reference is used to calculate the displayed value.

For **Input String** and **Output String** objects you can use form 7 and 9.

## Parameters

- **vt**: VT simulation node to apply the function
- **workingSetMaster**: Working Set Master which provides the object pool.
- **addressWorkingSetMaster**: Address of the Working Set Master which provides the object pool.
- **objectId**: Object ID.
- **value**: Returns the value of the object.
- **buffer**: After execution, this parameter contains the displayed string of an **Input String** or **Output String** object.
- **bufferLength**: Length of the buffer parameter in bytes.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3, 4, 9, 10

```c
long result;
double value;
result = VTIL_GetDisplayedValue(VT, 128, 206, value);  //Form 4 is used
switch (result)
{
  case 0:
    write("Displayed value of object 206 is '%f'", value);
    TestStepPass();
    break;
  case -2102: TestStepFail("Invalid object!"); break;
  case -2104: TestStepFail("Currently there is no active Working Set!"); break;
  case -2108: TestStepFail("Invalid variable reference!"); break;
  default:    TestStepFail("Unexpected error!"); break;
}
```
