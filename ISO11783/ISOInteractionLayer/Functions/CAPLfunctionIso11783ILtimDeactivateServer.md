[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimDeactivateServer.md)

# Iso11783IL_TIMDeactivateServer

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMDeactivateServer

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMDeactivateServer(); // form 1`
- `long Iso11783IL_TIMDeactivateServer(dword options); // form 2`
- `long Iso11783IL_TIMDeactivateServer(dbNode server); // form 3`
- `long Iso11783IL_TIMDeactivateServer(dbNode server, dword options); // form 4`

## Description

Deactivates the TIM server.

For a graceful shutdown, the TIM server gracefully releases all TIM functions being in automation. Then it sends three times in a row the Heartbeat counter value **Graceful shutdown**. And at the end, it stops sending any messages (including **TIM_ServerStatus_Msg**).

For a non-graceful shutdown, the TIM server stops sending any message at once, including **TIM_ServerStatus_Msg**.

## Parameters

- **options**: Additional options.
  - **Graceful shutdown**: `01h` - Server is gracefully shutdown

- **server**: TIM server node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
