[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimRemoveCertificate.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMRemoveCertificate

# Iso11783IL_TIMRemoveCertificate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMRemoveCertificate(byte certificateType); // form 1
long Iso11783IL_TIMRemoveCertificate(dbNode participant, byte certificateType); // form 2
```

## Description

Removes a certificate file which has been loaded Iso11783IL_TIMAddCertificate.

## Parameters

- **certificateType**: Type of certificate.
  - **0**: AEF Root certificate
  - **1**: Testlab certificate
  - **2**: Manufacturer certificate
  - **3**: Manufacturer series certificate
  - **4**: Device certificate
  - **5**: CRL signing certificate

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
