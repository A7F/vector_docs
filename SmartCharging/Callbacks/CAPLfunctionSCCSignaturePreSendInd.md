[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSignaturePreSendInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_SignaturePreSendInd

# SCC_SignaturePreSendInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SignaturePreSendInd(byte SessionId[], dword MessageId, byte Signature[], dword& SigLength)
```

## Description

This callback is called when a signature for a message has been created. It allows to peek for the signature and its length before it is sent with the indicated message. Also, both signature and length may be changed for the purpose of fault injection.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **[MessageID](SCC_MessageID.md)**: Type of the message that will use the signature.
- **Signature**: The signature data.
- **sigLength**: The number of signature data bytes. If set to zero, the signature will be absent in the indicated message.

## Return Values

—

## Example

```plaintext
SCC_SignaturePreSendInd( byte SessionID[], dword MessageID, byte Signature[], dword& SignatureLength)
{
  WriteLineEx(writeTab, 1, "SCC: Signature of length %i created for message %d", SignatureLength, MessageID);
}
```

[SCC_SignatureVerificationInd](CAPLfunctionSCCSignatureVerificationInd.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)