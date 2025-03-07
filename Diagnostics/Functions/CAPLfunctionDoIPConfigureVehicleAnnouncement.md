[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPConfigureVehicleAnnouncement.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » DoIP_ConfigureVehicleAnnouncement

# DoIP_ConfigureVehicleAnnouncement

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_ConfigureVehicleAnnouncement(dword toInitial_ms, dword messageCount, dword toInterval_ms);
```

## Description

Configures when the Vehicle Announcement Messages are sent.

## Parameters

- **toInitial_ms**  
  Initial timeout before sending the first announcement message after measurement start.

  **Note**  
  This parameter is ignored, if the function [DoIP_AnnounceVehicle](CAPLfunctionDoIPAnnounceVehicle.md) is used for sending Vehicle Announcement Messages.

- **messageCount**  
  Number of announcement messages sent when the measurement starts, or [DoIP_AnnounceVehicle](CAPLfunctionDoIPAnnounceVehicle.md) is called.

- **toInterval_ms**  
  Time between the announcement messages when more than 1 is configured.

## Return Values

—

## Example

```plaintext
// Send 5 announcement messages after 200 ms, with 100 ms interval
DoIP_ConfigureVehicleAnnouncement( 200, 5, 100);
DoIP_AnnounceVehicle();
```

[DoIP_GetAnnounceInterval](CAPLfunctionDoIPGetAnnounceInterval.md) • [DoIP_GetAnnounceMessageCount](CAPLfunctionDoIPGetAnnounceMessageCount.md) • [DoIP_GetAnnounceMessageCount](CAPLfunctionDoIPGetAnnounceWaitTime.md) • [DoIP_AnnounceVehicle](CAPLfunctionDoIPAnnounceVehicle.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)