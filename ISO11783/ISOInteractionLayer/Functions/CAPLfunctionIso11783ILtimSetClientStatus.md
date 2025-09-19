[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetClientStatus.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMSetClientStatus

# Iso11783IL_TIMSetClientStatus

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMSetClientStatus(dbNode server, dword cycleTime); // form 1`
- `long Iso11783IL_TIMSetClientStatus(dbNode server, dword cycleTime, pg TIM12 pgWithNewContent); // form 2`
- `long Iso11783IL_TIMSetClientStatus(dbNode client, dbNode server, dword cycleTime); // form 3`
- `long Iso11783IL_TIMSetClientStatus(dbNode client, dbNode server, dword cycleTime, pg TIM12 pgWithNewContent); // form 4`

## Description

Forms (1,3): This function changes the cycle time of the **TIM_ClientStatus_Msg message**. The content of **TIM_ClientStatus_Msg** message stays unchanged.

Forms (2,4): This function changes the content and cycle time of the **TIM_ClientStatus_Msg message**.

## Parameters

- **cycleTime**: Cycle time of the TIM_ClientStatus_Msg message [ms] (default: 100).
- **pgWithNewContent**: Content of this message is used by the following TIM_ClientStatus_Msg messages sent by the TIM client.
- **server**: The TIM client status message to this server is changed.
- **client**: TIM client node.

## Return Values

- **0**: Function has been executed successfully
- **1**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
