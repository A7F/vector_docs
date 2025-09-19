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
