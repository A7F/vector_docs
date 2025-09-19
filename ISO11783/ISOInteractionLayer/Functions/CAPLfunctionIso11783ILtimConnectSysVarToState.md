[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimConnectSysVarToState.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_TIMConnectSysVarToState

# Iso11783IL_TIMConnectSysVarToState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMConnectSysVarToState(dbNode counterpart, char[] sysVarNameWithPath); // form 1`
- `long Iso11783IL_TIMConnectSysVarToState(byte counterpartAddress, char[] sysVarNameWithPath); // form 2`
- `long Iso11783IL_TIMConnectSysVarToState(dbNode participant, dbNode counterpart, char[] sysVarNameWithPath); // form 3`
- `long Iso11783IL_TIMConnectSysVarToState(dbNode participant, byte counterpartAddress, char[] sysVarNameWithPath); // form 4`

## Description

Connects the state of a TIM client/server connection to a system variable.

You find the possible states in the tables of [Client States (TIM Component - ISO11783)](../TIMComponentClientStates.md) or [Server States (TIM Component - ISO11783)](../TIMComponentServerStates.md).

By means of the function you can wait for a specific state (e.g. using [TestWaitForSignalMatch](../../../Test/Functions/CAPLfunctionTestWaitForSignalMatch.md)) and with [Iso11783IL_TIMFreezeConnection](CAPLfunctionIso11783ILtimFreezeConnection.md) you can stay in this state.

To release connection between the system variable and a state, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **counterpart**: TIM counterpart of the client/server connection.
- **counterpartAddress**: Address of the TIM counterpart of the client/server connection. Value range: 0..253
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.
- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_TIMConnectSysVarToState(TIMClient, "sysvarTIMClientState");
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
