[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetResponseCode.md)

# SCC_SetResponseCode

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetResponseCode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**

This function can be called only in active mode, e.g., within a request callback to prepare the ResponseCode for the next response that will be sent by the EVSE simulation node. In passive mode use the function parameter of the respective `SCC_Create...` function to set the ResponseCode before calling [SCC_SendPreparedMessage](CAPLfunctionSCCSendPreparedMessage.md) to send the message.

## Function Syntax

`long SCC_SetResponseCode ( char ResponseCode[] )`

## Description

Sets the return code of the next message to be sent.

## Parameters

- **ResponseCode**: Response code string, which must match a valid enum value from the XMLSchema as defined by DIN70121 and ISO15118.

  **SAP Response Codes:**
  - OK_SuccessfulNegotiation
  - OK_SuccessfulNegotiationWithMinorDeviation
  - Failed_NoNegotiation

  **DIN Response Codes:**
  - OK
  - OK_NewSessionEstablished
  - OK_OldSessionJoined
  - OK_CertificateExpiresSoon
  - FAILED
  - FAILED_SequenceError
  - FAILED_ServiceIDInvalid
  - FAILED_UnknownSession
  - FAILED_ServiceSelectionInvalid
  - FAILED_PaymentSelectionInvalid
  - FAILED_CertificateExpired
  - FAILED_SignatureError
  - FAILED_NoCertificateAvailable
  - FAILED_CertChainError
  - FAILED_ChallengeInvalid
  - FAILED_ContractCanceled
  - FAILED_WrongChargeParameter
  - FAILED_PowerDeliveryNotApplied
  - FAILED_TariffSelectionInvalid
  - FAILED_ChargingProfileInvalid
  - FAILED_EVSEPresentVoltageToLow
  - FAILED_MeteringSignatureNotValid
  - FAILED_WrongEnergyTransferType
  - FAILED_RFIDPairing

  **ISO20 Response Codes:**
  - OK
  - OK_NewSessionEstablished
  - OK_OldSessionJoined
  - OK_CertificateExpiresSoon
  - FAILED
  - FAILED_SequenceError
  - FAILED_ServiceIDInvalid
  - FAILED_UnknownSession
  - FAILED_ServiceSelectionInvalid
  - FAILED_PaymentSelectionInvalid
  - FAILED_CertificateExpired
  - FAILED_SignatureError
  - FAILED_NoCertificateAvailable
  - FAILED_CertChainError
  - FAILED_ChallengeInvalid
  - FAILED_ContractCanceled
  - FAILED_WrongChargeParameter
  - FAILED_PowerDeliveryNotApplied
  - FAILED_TariffSelectionInvalid
  - FAILED_ChargingProfileInvalid
  - FAILED_MeteringSignatureNotValid
  - FAILED_NoChargeServiceSelected
  - FAILED_WrongEnergyTransferMode

  - FAILED_CertificateNotAllowedAtThisEVSE
  - FAILED_CertificateRevoked

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
