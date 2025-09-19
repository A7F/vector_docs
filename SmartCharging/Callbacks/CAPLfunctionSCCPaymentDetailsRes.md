[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPaymentDetailsRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » **SCC_PaymentDetailsRes**

# SCC_PaymentDetailsRes

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_PaymentDetailsRes ( byte SessionID[], long ResponseCode )
```

## Description

The callback is called as soon as a Service Payment Selection Response is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetTimestamp](../Functions/CAPLfunctionSCCGetTimestamp.md)
- [SCC_GetGenChallenge](../Functions/CAPLfunctionSCCGetGenChallenge.md)
- [SCC_GetResponseCodeString](../Functions/CAPLfunctionSCCGetResponseCodeString.md)

With [SCC_SetEnergyTransferType](../Functions/CAPLfunctionSCCSetEnergyTransferType.md) the transfer type/mode sent in the following message can be set.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **ResponseCode**: 1 if **OK**, 0 if **FAILED**.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
