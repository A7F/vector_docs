[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPConnectToVehicle.md)

**CAPL Functions** » **Diagnostics** » **DoIP_ConnectToVehicle**

# DoIP_ConnectToVehicle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

The function must not be called in an **on prestart** handler.

The following DoIP CAPL function is only available with the modeling library **DoIP.dll** and eventually an appropriate implementation of the CAPL Callback Interface. Information about the DoIP DLL and the CAPL Callback Interface you find here:

- [DoIP CAPL Introduction](../CAPLDiagnosticDoIP.md)
- [AN-IND-1-012_CAPL_Callback_Interface.pdf](javascript:startDemoLoader('AN-IND-1-012_CAPL_Callback_Interface.pdf'))
- [AN-IND-1-026_DoIP_in_CANoe.pdf](javascript:startDemoLoader('AN-IND-1-026_DoIP_in_CANoe.pdf'))

## Function Syntax

```plaintext
void DoIP_ConnectToVehicle();
```

## Description

Tries to connect to the configured vehicle. A vehicle identification phase may be started to retrieve the vehicle IP address.

## Parameters

—

## Return Values

—

## Example

```plaintext
// If key is pressed, connect to vehicle
On key 'c'
{
  DoIP_ConnectToVehicle();
}
```

[DoIP_VehicleConnectedInd](CAPLfunctionDoIPVehicleConnectedIndn.md) • [DoIP_CloseConnection](CAPLfunctionDoIPCloseConnection.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)