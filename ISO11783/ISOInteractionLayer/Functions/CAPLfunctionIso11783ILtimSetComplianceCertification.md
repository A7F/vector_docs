[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetComplianceCertification.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_TIMSetComplianceCertification

# Iso11783IL_TIMSetComplianceCertification

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetComplianceCertification(dword testProtocolPublicationYear, dword testProtocolRevision, dword laboratoryType, dword laboratoryID, dword referenceNumber); // form 1
long Iso11783IL_TIMSetComplianceCertification(dbNode participant, dword testProtocolPublicationYear, dword testProtocolRevision, dword laboratoryType, dword laboratoryID, dword referenceNumber); // form 2
```

## Description

Sets the content of message **ISOBUS Compliance Certification** (see ISO11783-7 B.27).

If the **ISOBUS Compliance Certification** message is in the Tx list of the TIM node and a Request for PGN 64834 (FD42h) is received then the **ISOBUS Compliance Certification** message is sent using the specified parameter (**ISOBUS Compliance Certification** message revision is always **1**).

## Parameters

- **testProtocolPublicationYear**: The publication year of the compliance test protocol to which the certification test was performed.  
  Range: 2000..2061.

- **testProtocolRevision**: Revision of the compliance test performed.  
  Range: 0..31.

- **laboratoryType**: Type of certification laboratory.
  - 0: Non-certified laboratory/self-certification
  - 1: AEF certified laboratory
  - 2: Reserved
  - 3: Not available (not certified)

- **laboratoryID**: Manufacturer code of the laboratory that performed the compliance test.  
  Range: 0..2047.

- **referenceNumber**: Certification reference number assigned by a certification laboratory.  
  Range: 0..65355.

- **participant**: TIM participant (TIM server or TIM client).

## Return Values

- **0**: Property has been set successfully
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
