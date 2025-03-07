[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetSelectedScheduleTableEntry.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Control](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimControl) » **SCC_SetSelectedScheduleTableEntry**

# SCC_SetSelectedScheduleTableEntry

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

## Function Syntax

```
long SCC_SetSelectedScheduleTableEntry ( long ID )
```

## Description

Sets the ID of the selected SAScheduleTuple, which is sent in the messages **PowerDeliveryReq** and **MeteringReceiptReq**.

**Note**  
For a valid charge session, use one of the SAScheduleTupleIDs sent by the charge point in the message **ChargeParameterDiscoveryRes**. You can query them using the function [SCC_GetSAScheduleTupleID](CAPLfunctionSCCGetSAScheduleTupleID.md). If no tuple is selected, the vehicle will automatically select the first or newest one.

## Parameters

- **ID**: Desired SAScheduleTupleID.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)