[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetSelectedService.md)

## SCC_SetSelectedService

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » SCC_SetSelectedService

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Note
This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

## Function Syntax

```plaintext
long SCC_SetSelectedService ( long ServiceID, long ParameterSetID )
```

## Description

Adds a service to the SelectedServiceList of the PaymentService-SelectionReq (former ServicePaymentSelectionReq) message.

### Note
For a correct message, use one of the ServiceIDs sent by the charge point in the message ServiceDiscoveryRes. The charge service is always selected automatically by the vehicle.

## Parameters

- **ServiceID**: ID of the desired service.
- **ParameterSetID**: ID of the desired parameter set (if set to 0, this optional parameter will be omitted).

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
