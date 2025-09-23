[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimFreezeConnection.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMFreezeConnection

# Iso11783IL_TIMFreezeConnection

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMFreezeConnection(dbNode counterpart, dword runToState); // form 1`
- `long Iso11783IL_TIMFreezeConnection(dbNode counterpart, dword runToState, char sysVarNameWithPath[]); // form 2`
- `long Iso11783IL_TIMFreezeConnection(byte counterpartAddress, dword runToState); // form 3`
- `long Iso11783IL_TIMFreezeConnection(byte counterpartAddress, dword runToState, char sysVarNameWithPath[]); // form 4`
- `long Iso11783IL_TIMFreezeConnection(dbNode participant, dbNode counterpart, dword runToState); // form 5`
- `long Iso11783IL_TIMFreezeConnection(dbNode participant, dbNode counterpart, dword runToState, char sysVarNameWithPath[]); // form 6`
- `long Iso11783IL_TIMFreezeConnection(dbNode participant, byte counterpartAddress, dword runToState); // form 7`
- `long Iso11783IL_TIMFreezeConnection(dbNode participant, dword runToState, char sysVarNameWithPath[]); // form 8`

## Description

After calling this function the TIM client or TIM server runs until the specified state is reached. In this state the node still sends the cyclic status messages.

You find the possible states in the tables of [Client States (TIM Component - ISO11783)](../TIMComponentClientStates.md) or [Server States (TIM Component - ISO11783)](../TIMComponentServerStates.md).

To continue the standard process you can call [Iso11783IL_TIMContinueConnection](CAPLfunctionIso11783ILtimContinueConnection.md).

For form 2, 4, 6 and 8 you can specify an additional system variable which is set to value **1** if the specified state is reached.

## Parameters

- **counterpart**: TIM counterpart of the client/server connection.
- **runToState**: The simulated TIM participant runs to this state and freezes this state.
- **counterpartAddress**: Address of the TIM counterpart of the client/server connection.
- **sysVarNameWithPath**: Name of a system variable (all namespaces inclusive) which is set to **1** if the state is reached.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
