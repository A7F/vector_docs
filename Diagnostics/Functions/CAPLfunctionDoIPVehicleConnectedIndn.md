[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDoIPVehicleConnectedIndn.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » _DoIP_VehicleConnectedInd

# _DoIP_VehicleConnectedInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void _DoIP_VehicleConnectedInd();
```

## Description

The TCP communications channel to the vehicle has been established successfully, i.e. diagnostic messages can be exchanged without further delays.

## Parameters

—

## Return Values

—

## Example

```c
void _DoIP_VehicleConnectedInd()
{
  write("Vehicle connected.");
}
```

[DoIP_ConnectToVehicle](CAPLfunctionDoIPConnectToVehicle.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)