[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILGetValueRawPhysical.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_GetValueRaw, TCIL_GetValuePhysical**

# TCIL_GetValueRaw, TCIL_GetValuePhysical

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_GetValueRaw(dbNode client, dword ddi, dword elementNumber, long & value); // form 1`
- `long TCIL_GetValueRaw(dword addressClient, dword ddi, dword elementNumber, long & value); // form 2`
- `long TCIL_GetValuePhysical(dbNode client, dword ddi, dword elementNumber, double & value); // form 3`
- `long TCIL_GetValuePhysical(dword addressClient, dword ddi, dword elementNumber, double & value); // form 4`
- `long TCIL_GetValueRaw(dbNode tc, dbNode client, dword ddi, dword elementNumber, long & value); // form 5`
- `long TCIL_GetValueRaw(dbNode tc, dword addressClient, dword ddi, dword elementNumber, long & value); // form 6`
- `long TCIL_GetValuePhysical(dbNode tc, dbNode client, dword ddi, dword elementNumber, double & value); // form 7`
- `long TCIL_GetValuePhysical(dbNode tc, dword addressClient, dword ddi, dword elementNumber, double & value); // form 8`

## Description

These functions return the current value of a data entity of the Task Controller. No **Request Value** command is sent.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the data entity belongs to.
- **addressClient**: Address of the Task Controller client node the data entity belongs to.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **elementNumber**: Element number, 0x000..0xFFF.
- **value**: Returns the value of the process data variable.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 5

```c
void CheckValue(double referenceValue)
{
  long result;
  double value;
  result = TCIL_GetValuePhysical(TC, Sprayer, 6, 1, value);
  if (result == 0)
  {
    if (value == referenceValue)
    {
      TestStepPass();
    }
    else
    {
      TestStepFail("CheckValue", "Value of data entity (DDI 6 , element number 1) is different (Expected value: %f)", referenceValue);
    }
  }
  else
  {
    TestStepFail("CheckValue", "Failed to get value of data entity (DDI 6 , element number 1). Error %i", result);
  }
}
```
