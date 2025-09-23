[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSignatureVerificationInd.md)

## SCC_SignatureVerificationInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_SignatureVerificationInd

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SignatureVerificationInd ( dword MessageID, dword SignatureValid )
```

### Description

The callback is called when a signed V2G message is verified with the ECDSA algorithm.

### Parameters

- **[MessageID](SCC_MessageID.md)**: Type of the received message.
- **SignatureValid**: 1 if the signature was verified as valid, 0 if the signature was verified as invalid.

### Return Values

—

### Example

—
