# DoIP_AnnounceVehicle

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

`void DoIP_AnnounceVehicle();`

## Description

Starts broadcasting Vehicle Announcement Messages.

**Note**  
The timing parameter **A_DoIP_Announce_Wait** in the DoIP.INI file as well as the parameter **toInitial_ms** configured with the function [DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md) are ignored when using this function, i.e. sending the Vehicle Announcement Messages starts without delay.

## Parameters

—

## Return Values

—

## Example

The number of messages sent and the time between sends can be configured in the DoIP.INI file and via [DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md).

```c
// Start broadcasting Vehicle Announcement Messages
DoIP_AnnounceVehicle();
```
