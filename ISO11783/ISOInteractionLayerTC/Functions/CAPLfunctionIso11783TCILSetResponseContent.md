[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILSetResponseContent.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_SetResponseContent

# TCIL_SetResponseContent

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_SetResponseContent(dbNode client, dword command, dword subcommand, pg pgPD); // form 1`
- `long TCIL_SetResponseContent(dword addressClient, dword command, dword subcommand, pg pgPD); // form 2`
- `long TCIL_SetResponseContent(dbNode tc, dbNode client, dword command, dword subcommand, pg pgPD); // form 3`
- `long TCIL_SetResponseContent(dbNode tc, dword addressClient, dword command, dword subcommand, pg pgPD); // form 4`

## Description

The function changes the content of the next TC response TC12 sent by the TC IL to allow fault injection.

## Parameters

- **tc**: TC simulation node to apply the function.
- **client**: Task Controller client which is the originator of the command and receiver of the response message.
- **addressClient**: Address of the Task Controller client which is the originator of the command and receiver of the response message.
- **command**: Refers to the response with this command value, 0..15.
- **subcommand**: Refers to the response with this subcommand value (is only used if command is 0 or 1), 0..15.
- **pgPD**: This message replaces the Process Data response of the Task Controller IL.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

Example form 3

```plaintext
long result;
pg PD pgPD;
J1939InitPGData (pgPD);
pdgPD.Command = 1; // Subcommand for the transfer and management of device descriptors
pgPD.DeviceDescriptionMsgType = 5; // Request Object Pool Transfer response
pgPD.Status = 1; // Not enough memory available
result = TCIL_SetResponseContent(TC, Sprayer, 1, 5, pgPD);
if (result < 0)
{
  TestStepFail("Failed to modify Request Object Pool response");
}
```
