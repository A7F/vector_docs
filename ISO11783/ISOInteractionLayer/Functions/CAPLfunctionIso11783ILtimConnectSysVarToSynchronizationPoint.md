[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimConnectSysVarToSynchronizationPoint.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMConnectSysVarToSynchronizationPoint

# Iso11783IL_TIMConnectSysVarToSynchronizationPoint

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_TIMConnectSysVarToSynchronizationPoint(dbNode counterpart, char[] sysVarNameWithPath);` // form 1
- `long Iso11783IL_TIMConnectSysVarToSynchronizationPoint(byte counterpartAddress, char[] sysVarNameWithPath);` // form 2
- `long Iso11783IL_TIMConnectSysVarToSynchronizationPoint(dbNode participant, dbNode counterpart, char[] sysVarNameWithPath);` // form 3
- `long Iso11783IL_TIMConnectSysVarToSynchronizationPoint(dbNode participant, byte counterpartAddress, char[] sysVarNameWithPath);` // form 4

## Description

Connects the synchronization point of a TIM client/server connection to a system variable. Possible values of the system variables are:

- 0: Authentication not started
- 1: Authentication started
- 2: Authenticated

To release connection between the system variable, just call the same method again, but with the empty string instead of the name of system variable.

## Parameters

- **counterpart**: TIM counterpart of the client/server connection.
- **counterpartAddress**: Address of the TIM counterpart of the client/server connection. Value range: 0..253
- **sysVarNameWithPath**: Name of the system variable, all namespaces inclusive.
- **participant**: Simulation node (TIM server or TIM client) to apply the function.

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_TIMConnectSysVarToSynchronizationPoint (TIMClient, "Server::SynchPoint");
```
