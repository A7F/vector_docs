[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILDelayRxMessage.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_DelayRxMessage**

# TCIL_DelayRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_DelayRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay); // form 1`
- `long TCIL_DelayRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay, char sysVarNameWithPath[]); // form 2`
- `long TCIL_DelayRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay); // form 3`
- `long TCIL_DelayRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay, char sysVarNameWithPath[]); // form 4`

## Description

A message described in the function is only forwarded to the simulation node after the defined delay. As a result, the simulated node reacts to the message only after this delay.

You can also define a system variable which is set if the specified message is received.

To revert this command you can use [TCIL_ResetDelayedRxMessage](CAPLfunctionIso11783TCILResetDelayedRxMessage.md) or [TCIL_ResetAllDelayedRxMessage](CAPLfunctionIso11783TCILResetAllDelayedRxMessage.md).

## Parameters

- **pgn**: Parameter Group Number (with data page) of the message to be delayed.
- **sourceAddress**: Source address of the message to be delayed (or 0xFFFFFFFF if the source address is to be ignored).
- **filterMask**: Defines the bits of the first 8 Bytes of the message payload which shall be used to identify (filter) the message. Use value 0 if you don’t want to filter by message payload.
- **filterValue**: Defines the value of the bits of the first 8 bytes of the message payload which shall be used to identify (filter) the message. If the value of the bits of a received message identified by **filterMask** is equal to this value, this message is delayed.
- **sysVarNameWithPath**: Name of a system variable (all namespaces inclusive) which is set to 1 if the specified message is received. You can specify an empty string if no system variable shall be used.
- **delay**: Delay in [ms]. After this delay the message is forwarded to the simulated node. If delay is **0** then the message is forwarded without any delay (e.g. if you only want to wait for the message using the specified system variable and the function [testWaitForSysVar](../../../Test/Functions/CAPLfunctionTestWaitForSysVar.md)).
- **node**: Simulation node to apply the function.

## Return Values

- **0**: Function has been executed successfully
- **-102**: An invalid parameter is used

## Example

—
