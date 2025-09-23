# OnSecurityLocalPDUValidatedWithOemInfo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces OnSecurityLocalPDUValidated and respectively OnLocalSecurityPDUValidated.

## Function Syntax

```plaintext
void OnSecurityLocalPDUValidatedWithOemInfo(char pduName[], dword dataId, byte payload[], dword payloadLength, qword pduExtractedAuthInfoHigh, qword pduExtractedAuthInfo, dword pduExtractedAuthInfoBitLength, qword pduExtractedFreshness, dword pduExtractedFreshnessBitLength, dword freshnessValueId, dword verificationResult, long oemSpecificFailureReason, qword freshnessValueUsedToValidatePDU, dword freshnessBitLengthUsedToValidatePDU)
```

## Description

This callback handler is called when a secured PDU is received in the node. Besides the verification result, all values used for verification can be analyzed. It provides information about the specific error if the validation failed. Additionally, you get information about the freshness value and length used for the validation.

The parameter VerificationResult indicates if the validation was successful or not.

## Parameters

- **pduName[]**: The name of the PDU.
- **dataId**: The used Data-ID.
- **payload**: The byte array with the received data.
- **payloadLength**: The length of the payload array in bytes.
- **pduExtractedAuthInfoHigh**: Received authentication (MAC). Bytes 8-15. (Not relevant for RNA)
- **pduExtractedAuthInfo**: Received authentication (MAC). Bytes 0-7.
- **pduExtractedAuthInfoBitLength**: Length of the Authentication in bit.
- **pduExtractedFreshness**: Received Freshness value from PDU.
- **pduExtractedFreshnessBitLength**: Length of the Freshness in bit.
- **freshnessValueId**: Freshness value id.
- **verificationResult**: Verification result.
  - Not verified = 0
  - Verified = 1
- **oemSpecificFailureReason**: OEM security specific error codes, which give additional information about why the validation failed.
- **freshnessValueUsedToValidatePDU**: The (full) freshness value used to validate the PDU.
- **freshnessBitLengthUsedToValidatePDU**: The freshness length in bits used to validate the PDU.

## Return Values

—

## Example

—

[OnSecurityOfNodePDUValidatedWithOemInfo](CAPLfunctionOnSecurityOfNodePDUValidatedWithOemInfo.md)
