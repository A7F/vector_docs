[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPaymentDetailsReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_PaymentDetailsReq**

# SCC_PaymentDetailsReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_PaymentDetailsReq ( byte SessionID[], char ContractID[] )
```

## Description

The callback is called as soon as a Payment Details Request is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetCertificateChainData](../Functions/CAPLfunctionSCCGetCertificateChainData.md)
- [SCC_GetCertificateChainCertificate](../Functions/CAPLfunctionSCCGetCertificateChainCertificate.md)

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ContractID**: ID of the contract to which the certificate is assigned, max. 128 character string. (eMAID)

## Return Values

—

## Example

—
