[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetValueRawPhysical.md)

CAPL Functions » ISO11783 » Task Controller Interaction Layer (TC IL) » TCIL_SetValueRaw, TCIL_SetValuePhysical

# TCIL_SetValueRaw, TCIL_SetValuePhysical

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetValueRaw(dbNode client, dword ddi, dword elementNumber, long value); // form 1`
- `long TCIL_SetValueRaw(dword addressClient, dword ddi, dword elementNumber, long value); // form 2`
- `long TCIL_SetValueRaw(dbNode tc, dbNode client, dword ddi, dword elementNumber, long value); // form 3`
- `long TCIL_SetValueRaw(dbNode tc, dword addressClient, dword ddi, dword elementNumber, long value); // form 4`
- `long TCIL_SetValuePhysical(dbNode client, dword ddi, dword elementNumber, double value); // form 5`
- `long TCIL_SetValuePhysical(dword addressClient, dword ddi, dword elementNumber, double value); // form 6`
- `long TCIL_SetValuePhysical(dbNode tc, dbNode client, dword ddi, dword elementNumber, double value); // form 7`
- `long TCIL_SetValuePhysical(dbNode tc, dword addressClient, dword ddi, dword elementNumber, double value); // form 8`

## Description

These functions set the value of a data entity without sending any command.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the data entity belongs to.
- **addressClient**: Address of the Task Controller client node the data entity belongs to.
- **elementNumber**: Element number, 0x000..0xFFF.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **value**: New value of the data entity.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 7

```c
void SetSetpointMassPerAreaApplicationRate(double value)
{
    long result;
    result = TCIL_SetValuePhysical(TC, Sprayer, 6, 1, value);
    switch (result)
    {
        case 0: TestStepPass(); break;
        case -2202: TestStepFail("Function is not available in passive mode of the TC IL!"); break;
        case -2204: TestStepFail("Node 'Sprayer' is no client device!"); break;
        default: TestStepFail("Unexpected error"); break;
    }
}
```
