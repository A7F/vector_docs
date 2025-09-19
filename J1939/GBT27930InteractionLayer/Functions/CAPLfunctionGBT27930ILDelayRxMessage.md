[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GBT27930InteractionLayer/Functions/CAPLfunctionGBT27930ILDelayRxMessage.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [GB/T 27930 IL](../CAPLfunctionsGBT27930ILOverview.md) » GBT27930IL_DelayRxMessage

# GBT27930IL_DelayRxMessage

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GBT27930IL_DelayRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay); // form 1`
- `long GBT27930IL_DelayRxMessage(dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay, char sysVarNameWithPath[]); // form 2`
- `long GBT27930IL_DelayRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay); // form 3`
- `long GBT27930IL_DelayRxMessage(dbNode node, dword pgn, dword sourceAddress, qword filterMask, qword filterValue, dword delay, char sysVarNameWithPath[]); // form 4`

## Description

A message described in the function is only forwarded to the simulation node after the defined delay. As a result, the simulated node reacts to the message only after this delay.

You can also define a system variable which is set if the specified message is received.

To revert this command you can use [GBT27930IL_ResetDelayedRxMessage](CAPLfunctionGBT27930ILResetDelayedRxMessage.md) or [GBT27930IL_ResetAllDelayedRxMessage](CAPLfunctionGBT27930ILResetAllDelayedRxMessage.md).

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

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
