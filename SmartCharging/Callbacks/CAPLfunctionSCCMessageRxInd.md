[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCMessageRxInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » **SCC_MessageRxInd**

# SCC_MessageRxInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_MessageRxInd(byte SessionID[], dword MessageID)
```

## Description

The callback is called each time a Vehicle2Grid, SECC Discovery or SLAC message is received by the simulation DLL.

## Parameters

- **SessionID**  
  8-byte long SessionID of the connection, range: 0 - 0xFF FF FF FF FF FF FF FF

- **[MessageID](SCC_MessageID.md)**  
  Type of received message:
  - For SLAC messages, MMType (2 byte) according to specification.
  - For V2G messages see help page [MessageID](SCC_MessageID.md).

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
