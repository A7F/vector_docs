[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimAddCertificate.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMAddCertificate**

# Iso11783IL_TIMAddCertificate

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMAddCertificate(byte certificateType, char certificateFilePath[]); // form 1
long Iso11783IL_TIMAddCertificate(dbNode participant, byte certificateType, char certificateFilePath[]); // form 2
```

## Description

Loads a certificate file which is used for TIM authentication. If there is already a loaded certificate file for a certificate type, this file is overwritten.

## Parameters

- **certificateType**: Type of certificate.
  - **0**: AEF Root certificate
  - **1**: Testlab certificate
  - **2**: Manufacturer certificate
  - **3**: Manufacturer series certificate
  - **4**: Device certificate
  - **5**: CRL signing certificate

  The CRLs are loaded with a separate function.

- **certificateFilePath**: Path of a certificate file (DER file format). Path has to be absolute or relative relating to the folder of the CANoe configuration.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
