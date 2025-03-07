[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecCertificateValidIdentifiedRegion.md)

**CAPL Functions** » **Car2x** » **C2xSecCertificateValidIdentifiedRegion**

# C2xSecCertificateValidIdentifiedRegion

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecCertificateValidIdentifiedRegion(long certHdl, dword countryId, dword checkChain);
```

## Description

Validates the validity of a certificate region.

## Parameters

- **certHdl**: Handle of the certificate to be tested.
- **countryId**: Country code.
- **checkChain**: If set to 1, the whole certificate chain is tested (recommended).

## Return Values

- **kValidOk**: 0x00,
- **kValidError**: 0x01, // unknown / wrong parameter
- **kValidChainIncomplete**: 0x02,
- **kValidChainInvalid**: 0x03, // wrong signature or root not reliable
- **kValidConditionNotMet**: 0x04, // country-id or ssp/msk not allowed

## Example

```plaintext
variables
{
  dword myCertHdl;
}

on start
{
  myCertHdl = C2xSecCertificateGetHandle("MyCert");

  write("Country: %d",
    C2xSecCertificateValidIdentifiedRegion(certHdl, 276, 1));
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)