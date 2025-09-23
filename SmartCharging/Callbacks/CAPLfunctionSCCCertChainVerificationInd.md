[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCertChainVerificationInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » **SCC_CertChainVerificationInd**

# SCC_CertChainVerificationInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CertChainVerificationInd ( byte SessionId[], char ChainName[], dword ChainIsValid )
```

## Description

The callback is called when a received certificate chain (e.g. `ContractSignatureCertChain`) is verified. Certificate chains are sent as part of several V2G messages when in PnC mode. The callback may be called multiple times for a V2G message, if that message contains multiple chains.

In case of errors, the specific error cause(s) can be queried with the function `SCC_GertCertChainVerificationDetails`.

A list of individual verification errors can be queried with:

- [SCC_GetCertChainVerificationErrorCount](../Functions/CAPLfunctionSCCGetCertChainVerificationErrorCount .md)
- [SCC_GetCertChainVerificationError](../Functions/CAPLfunctionSCCGetCertChainVerificationError.md)

## Parameters

- **SessionId**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ChainName**: Name of the verified certificate chain inside the V2G message.
- **ChainIsValid**: 1 if the chain was verified as valid, 0 if the chain was verified as invalid.

## Return Values

—

## Example

—

[SCC_GetCertChainVerificationError](../Functions/CAPLfunctionSCCGetCertChainVerificationError.md) • [SCC_GetCertChainVerificationErrorCount](../Functions/CAPLfunctionSCCGetCertChainVerificationErrorCount .md)
