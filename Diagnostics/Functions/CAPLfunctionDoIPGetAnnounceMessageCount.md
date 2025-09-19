# DoIP_GetAnnounceMessageCount

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_GetAnnounceMessageCount

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

`dword DoIP_GetAnnounceMessageCount();`

## Description

Gets the number of configured Vehicle Announcement Messages to be sent by a vehicle simulation.

## Parameters

—

## Return Values

The number of configured vehicle announcement messages (configured in the DoIP.INI or via [DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md)).

## Example

—

•• [DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md) ••
