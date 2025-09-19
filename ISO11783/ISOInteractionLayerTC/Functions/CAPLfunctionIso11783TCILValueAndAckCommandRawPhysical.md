[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILValueAndAckCommandRawPhysical.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ValueAndAckCommand, TCIL_ValueAndAckCommandRaw, TCIL_ValueAndAckCommandPhysical**

# TCIL_ValueAndAckCommand, TCIL_ValueAndAckCommandRaw, TCIL_ValueAndAckCommandPhysical

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ValueAndAckCommand(dbNode client, dword ddi, dword elementNumber); // form 1`
- `long TCIL_ValueAndAckCommand(dword addressClient, dword ddi, dword elementNumber); // form 2`
- `long TCIL_ValueAndAckCommand(dbNode tc, dbNode client, dword ddi, dword elementNumber); // form 3`
- `long TCIL_ValueAndAckCommand(dbNode tc, dword addressClient, dword ddi, dword elementNumber); // form 4`
- `long TCIL_ValueAndAckCommandRaw(dbNode client, dword ddi, dword elementNumber, long value); // form 5`
- `long TCIL_ValueAndAckCommandRaw(dword addressClient, dword ddi, dword elementNumber, long value); // form 6`
- `long TCIL_ValueAndAckCommandRaw(dbNode tc, dbNode client, dword ddi, dword elementNumber, long value); // form 7`
- `long TCIL_ValueAndAckCommandRaw(dbNode tc, dword addressClient, dword ddi, dword elementNumber, long value); // form 8`
- `long TCIL_ValueAndAckCommandPhysical(dbNode client, dword ddi, dword elementNumber, double value); // form 9`
- `long TCIL_ValueAndAckCommandPhysical(dword addressClient, dword ddi, dword elementNumber, double value); // form 10`
- `long TCIL_ValueAndAckCommandPhysical(dbNode tc, dbNode client, dword ddi, dword elementNumber, double value); // form 11`
- `long TCIL_ValueAndAckCommandPhysical(dbNode tc, dword addressClient, dword ddi, dword elementNumber, double value); // form 12`

## Description

Form (1) and (3) send the current value of the specified data entity to the client with **Set Value and Acknowledge command**. It can be used to send to the client the previously set Compressed State DDIs DDIs (using [TCIL_SetValueRaw](CAPLfunctionIso11783TCILSetValueRawPhysical.md) or [TCIL_SetValuePhysical](CAPLfunctionIso11783TCILSetValueRawPhysical.md)).

Form (5)-(12) set the value to the specified data entity and send the value to the client with **Set Value and Acknowledge command**.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the TC sends the **Set Value and Acknowledge command** to.
- **addressClient**: Address of the Task Controller client node the TC sends the **Set Value and Acknowledge command** to.
- **elementNumber**: Element number, 0x000..0xFFF.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **value**: New value of the data entity.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 11

```c
void SendSetpointMassPerAreaApplicationRate(double value)
{
    long result;
    result = TCIL_ValueAndAckCommandPhysical(TC, Sprayer, 6, 1, value);
    switch (result)
    {
        case 0: TestStepPass(); break;
        case -2202: TestStepFail("Function is not available in passive mode of the TC IL!"); break;
        case -2204: TestStepFail("Node 'Sprayer' is no client device!"); break;
        case -2210: TestStepFail("Failed to send Value command!"); break;
        default: TestStepFail("Unexpected error"); break;
    }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
