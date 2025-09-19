[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetProcessing.md)

# SCC_SetProcessing

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetProcessing

Valid for:  CANoe DE •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

`long SCC_SetProcessing ( long Processing )`

## Description

Sets the processing status of the charge point. This status is used for controlling various message loops, where the vehicle will continue sending the same request until EVSEProcessing is set to **Finished** within the response message.

**Note**  
The charge point will never send EVSEProcessing = **Ongoing** unless this function is called. The special value **Ongoing_WaitingForCustomerInteraction** of ISO IS will automatically be applied according to [V2G2-854] if EVSEProcessing was set to 1.

## Parameters

- **EVSEProcessing**
  - 0 if **Finished**
  - 1 if **Ongoing** resp. **Ongoing_WaitingForCustomerInteraction** (ISO 15118)

## Return Values

- **0**  
  Not successful
- **1**  
  Successful

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
