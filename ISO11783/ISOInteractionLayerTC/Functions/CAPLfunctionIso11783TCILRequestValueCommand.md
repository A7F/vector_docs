[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILRequestValueCommand.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_RequestValueCommand**

# TCIL_RequestValueCommand

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_RequestValueCommand(dbNode client, dword ddi, dword elementNumber); // form 1`
- `long TCIL_RequestValueCommand(dword addressClient, dword ddi, dword elementNumber); // form 2`
- `long TCIL_RequestValueCommand(dbNode tc, dbNode client, dword ddi, dword elementNumber); // form 3`
- `long TCIL_RequestValueCommand(dbNode tc, dword addressClient, dword ddi, dword elementNumber); // form 4`

## Description

This function sends the **Request Value** command to the client.

## Parameters

- **tc**: Task Controller simulation node to apply the function.
- **client**: Task Controller client node the TC sends the **Request Value** command to.
- **addressClient**: Address of the Task Controller client node the TC sends the **Request Value** command to.
- **ddi**: Data dictionary identifier, 0x0000..0xFFFF.
- **elementNumber**: Element number, 0x000..0xFFF.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
long result;
result = TCIL_RequestValueCommand(TC, Sprayer, 6, 3);
if (result != 0)
{
  TestStepFail("RequestValue", "Failed to request value of data entity (DDI 6 , element number 1). Error %i", result);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)