[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetShutdownRequest.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » **SCC_SetShutdownRequest**

# SCC_SetShutdownRequest

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetShutdownRequest ( long ShutdownRequest )
```

## Description

Demands the stop of the charging session from the vehicle, the appropriate mechanism for the active schema version, or withdraws this request.

**Note**: You can still initiate a shutdown using the specific parameter of the target schema version instead of using this convenience function.

## Parameters

- **ShutdownRequest**
  - 1 to demand a shutdown.
  - 0 to withdraw a shutdown request.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)