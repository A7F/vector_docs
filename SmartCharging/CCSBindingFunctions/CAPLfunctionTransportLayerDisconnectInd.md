[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionTransportLayerDisconnectInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » TransportLayerDisconnectInd

# TransportLayerDisconnectInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void TransportLayerDisconnectInd ( uint32 Port, bool IsInitiator )
```

## Description

This callback is called as soon as a TCP connection is closed.

## Parameters

- **Port**: Port number of the TCP connection
- **IsInitiator**:
  - 1 if the simulation DO initiated the shutdown.
  - 0 if the simulation DO received the shutdown request.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)