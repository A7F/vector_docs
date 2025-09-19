[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetCertificateSequence.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetCertificateSequence

# Iso11783IL_TIMSetCertificateSequence

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetCertificateSequence(dword certificateType1, dword certificateType2, dword certificateType3, dword certificateType4); // form 1
long Iso11783IL_TIMSetCertificateSequence(dbNode participant, dword certificateType1, dword certificateType2, dword certificateType3, dword certificateType4); // form 2
```

## Description

Sets the sequence of requested certificates.

Use this function to change the sequence of requested certificates. By default the following sequence is used:

- Testlab certificate
- Manufacturer certificate
- Manufacturer series certificate
- Device certificate

## Parameters

- **certificateType1**: Type of first requested certificate.
  - Values:
    - `1`: Testlab certificate
    - `2`: Manufacturer certificate
    - `3`: Manufacturer series certificate
    - `4`: Device certificate
  - Default value: 1 (Testlab certificate).

- **certificateType2**: Type of second requested certificate.
  - Default value: 2 (Manufacturer certificate).

- **certificateType3**: Type of third requested certificate.
  - Default value: 3 (Manufacturer series certificate).

- **certificateType4**: Type of fourth requested certificate.
  - Default value: 4 (Device certificate).

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
