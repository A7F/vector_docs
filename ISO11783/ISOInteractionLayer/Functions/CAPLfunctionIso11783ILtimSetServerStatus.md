[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetServerStatus.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetServerStatus

# Iso11783IL_TIMSetServerStatus

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMSetServerStatus(dword cycleTime); // form 1`
- `long Iso11783IL_TIMSetServerStatus(dword cycleTime, pg TIM12 pgWithNewContent); // form 2`
- `long Iso11783IL_TIMSetServerStatus(dbNode server, dword cycleTime); // form 3`
- `long Iso11783IL_TIMSetServerStatus(dbNode server, dword cycleTime, pg TIM12 pgWithNewContent); // form 4`

## Description

- **Forms (1, 3):** This function changes the cycle time of the **TIM_ServerStatus_Msg** message. The content of **TIM_ServerStatus_Msg** message stays unchanged.
- **Forms (2, 4):** This function changes the content and cycle time of the **TIM_ServerStatus_Msg** message.

## Parameters

- **cycleTime**: Cycle time of the **TIM_ServerStatus_Msg** message [ms] (default: 100).
- **pgWithNewContent**: Content of this message is used by the following **TIM_ServerStatus_Msg** messages sent by the TIM server.
- **server**: TIM server node.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)