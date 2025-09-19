[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACGetMSoundTarget.md)

# SCC_SLAC_GetMSoundTarget

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Data Queries](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#SLACSim) » SCC_SLAC_GetMSoundTarget

**Valid for**:  CANoe DE • CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_SLAC_GetMSoundTarget(byte MSoundTarget[])
```

## Description

Gets the target MAC Address for the M-Sounds (mandatory value: broadcast address).

## Parameters

- **MSoundTarget**: Queries the address (6 byte) (to the given byte buffer).

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
