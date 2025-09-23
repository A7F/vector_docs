[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetAuthenticationBusyMode.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetAuthenticationBusyMode

# Iso11783IL_TIMSetAuthenticationBusyMode

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetAuthenticationBusyMode(dword activate); // form 1
long Iso11783IL_TIMSetAuthenticationBusyMode(dbNode* timParticipant, dword activate); // form 2
```

## Description

Activates or deactivates the authentication busy mode.

If the busy mode is activated:

- Message **Auth_ServerAuthenticationStatus** or **Auth_ClientAuthenticationStatus** is sent with error code **Participant busy**.
- Certificate requests or challenge requests are responded with error code **Participant busy**.

## Parameters

- **activate**
  - 0: Busy mode is deactivated
  - 1: Busy mode is activated

- **participant**
  - TIM participant (TIM server or TIM client).

## Return Values

- **0**
  - Property has been set successfully

- **< 0**
  - An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
