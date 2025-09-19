# DoIP_GetAnnounceInterval

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```
dword DoIP_GetAnnounceInterval();
```

## Description

Gets the time between the Vehicle Announcement Messages sent by a vehicle simulation (in milliseconds).

## Parameters

—

## Return Values

Time between the sent vehicle announcement messages (configured in the DoIP.INI or via [DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md)).

## Example

—

[DoIP_ConfigureVehicleAnnouncement](CAPLfunctionDoIPConfigureVehicleAnnouncement.md)
