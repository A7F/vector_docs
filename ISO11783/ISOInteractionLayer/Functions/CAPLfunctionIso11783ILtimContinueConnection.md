[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimContinueConnection.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMContinueConnection

# Iso11783IL_TIMContinueConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMContinueConnection(dbNode counterpart); // form 1`
- `long Iso11783IL_TIMContinueConnection(dbNode counterpart, dword nextState); // form 2`
- `long Iso11783IL_TIMContinueConnection(byte counterpartAddress); // form 3`
- `long Iso11783IL_TIMContinueConnection(byte counterpartAddress, dword nextState); // form 4`
- `long Iso11783IL_TIMContinueConnection(dbNode participant, dbNode counterpart); // form 5`
- `long Iso11783IL_TIMContinueConnection(dbNode participant, dbNode counterpart, dword nextState); // form 6`
- `long Iso11783IL_TIMContinueConnection(dbNode participant, byte counterpartAddress); // form 7`
- `long Iso11783IL_TIMContinueConnection(dbNode participant, byte counterpartAddress, dword nextState); // form 8`

## Description

Continues a connection which has been frozen by [Iso11783IL_TIMFreezeConnection](CAPLfunctionIso11783ILtimFreezeConnection.md).

- Form 1, 3, 5, and 7 continues the state of the currently frozen connection by execution the action of this state.
- Form 2, 4, 6 and 8 continues with the specified state and executes the action of this state.

## Parameters

- **counterpart**: TIM counterpart of the client/server connection.
- **counterpartAddress**: Address of TIM counterpart of the client/server connection.
- **nextState**: ID of the next state.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
