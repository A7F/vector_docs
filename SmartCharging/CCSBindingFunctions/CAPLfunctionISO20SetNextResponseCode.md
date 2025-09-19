[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionISO20SetNextResponseCode.md)

# SetNextResponseCode

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetNextResponseCode

Valid for:  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
MethodReturnValueType SetNextResponseCode(ISO20ResponseCodeType ISO20ResponseCode);
MethodReturnValueType SetNextResponseCode(SAPResponseCodeType SAPResponseCode);
```

## Description

This function is used on the respective embedded member to overwrite the next ResponseCode sent in a response message. It is available for the following embedded members:

- SAP
- ISO20
- ScheduleRenegotiation (using the ISO20ResponseCodeType)

## Parameters

**SAPResponseCode**

Enum with following values:

- 0 = OK_SuccessfulNegotiation
- 1 = OK_SuccessfulNegotiationWithMinorDeviation
- 2 = FAILED_NoNegotiation

**ISO20ResponseCode**

Enum with following values:

- 0 = OK
- 1 = OK_CertificateExpiresSoon
- 2 = OK_NewSessionEstablished
- 3 = OK_OldSessionJoined
- 4 = OK_PowerToleranceConfirmed
- 5 = WARNING_AuthorizationSelectionInvalid
- 6 = WARNING_CertificateExpired
- 7 = WARNING_CertificateNotYetValid
- 8 = WARNING_CertificateRevoked
- 9 = WARNING_CertValidationError
- 10 = WARNING_ChallengeInvalid
- 11 = WARNING_EIMAuthorizationFailure
- 12 = WARNING_E_MSPUnknown
- 13 = WARNING_EVPowerProfileViolation
- 14 = WARNING_GeneralPNCAuthorizationError
- 15 = WARNING_NoCertificateAvailable
- 16 = WARNING_NoContractMatchingPCIDFound
- 17 = WARNING_PowerToleranceNotConfirmed
- 18 = WARNING_ScheduleRenegotiationFailed
- 19 = WARNING_StandbyNotAllowed
- 20 = WARNING_WPT
- 21 = FAILED
- 22 = FAILED_AssociationError
- 23 = FAILED_ContactorError
- 24 = FAILED_EVPowerProfileInvalid
- 25 = FAILED_EVPowerProfileViolation
- 26 = FAILED_MeteringSignatureNotValid
- 27 = FAILED_NoEnergyTransferServiceSelected
- 28 = FAILED_NoServiceRenegotiationSupported
- 29 = FAILED_PauseNotAllowed
- 30 = FAILED_PowerDeliveryNotApplied
- 31 = FAILED_PowerToleranceNotConfirmed
- 32 = FAILED_ScheduleRenegotiation
- 33 = FAILED_ScheduleSelectionInvalid
- 34 = FAILED_SequenceError
- 35 = FAILED_ServiceIDInvalid
- 36 = FAILED_ServiceSelectionInvalid
- 37 = FAILED_SignatureError
- 38 = FAILED_UnknownSession
- 39 = FAILED_WrongChargeParameter

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
