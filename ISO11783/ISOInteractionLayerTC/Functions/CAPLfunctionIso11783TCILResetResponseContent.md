[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetResponseContent.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_ResetResponseContent**

# TCIL_ResetResponseContent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetResponseContent(dbNode client, dword command, dword subcommand); // form 1`
- `long TCIL_ResetResponseContent(dword addressClient, dword command, dword subcommand); // form 2`
- `long TCIL_ResetResponseContent(dbNode tc, dbNode client, dword command, dword subcommand); // form 3`
- `long TCIL_ResetResponseContent(dbNode tc, dword addressClient, dword command, dword subcommand); // form 4`

## Description

The function resets the modification of TCIL_SetResponseContent. The TC IL returns to the default response behavior.

## Parameters

- **tc**: TC simulation node to apply the function.
- **client**: Task Controller client which is the originator of the command and receiver of the response message.
- **addressClient**: Address of the Task Controller client which is the originator of the command and receiver of the response message.
- **command**: Refers to the response with this command value, 0..15.
- **subcommand**: Refers to the response with this subcommand value (is only used if command is 0 or 1), 0..15.

## Return Values

- **0**: Function has been executed successfully
- **< 0**: An error has occurred, see [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```c
long result;
result = TCIL_ResetResponseContent(TC, Sprayer, 168);
if (result < 0)
{
  TestStepFail("Failed to reset fault injection");
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
