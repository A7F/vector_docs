[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPrivateKeyVerificationInd.md)

# SCC_PrivateKeyVerificationInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EV Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEV) » SCC_PrivateKeyVerificationInd

**Valid for**:  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_PrivateKeyVerificationInd ( byte SessionId[], dword KeyIsValid )
```

## Description

The callback is called when a received encrypted private key (e.g. ContractSignatureEncryptedPrivateKey) is verified. The private key is sent as part of Certificate Installation and Certificate Update Responses.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **KeyIsValid**: 1 if the key was verified as valid, 0 if the key was verified as invalid.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
