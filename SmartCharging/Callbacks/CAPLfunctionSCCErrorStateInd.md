[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCErrorStateInd.md)

# SCC_ErrorStateInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_ErrorStateInd

**Valid for**:  CANoe DE • CANoe4SW DE

**Note**  
The error state is active until the timer for a protocol restart expires.

## Function Syntax

```plaintext
void SCC_ErrorStateInd ( byte SessionID[], long ErrorState )
```

## Description

The callback is called as soon as the node enters or exits the error state.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ErrorState**: 1 if the error state is entered, 0 if it is exited.

## Return Values

—

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
