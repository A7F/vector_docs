[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCProtocolFinishedInd.md)

## SCC_ProtocolFinishedInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_ProtocolFinishedInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

### Function Syntax

```plaintext
void SCC_ProtocolFinishedInd ( byte SessionID[] )
```

### Description

The callback is called when a protocol run has been successfully finished.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.

### Return Values

—

### Example

—
