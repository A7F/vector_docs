[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecCertificateValidAppSspBitmap.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecCertificateValidAppSspBitmap

# C2xSecCertificateValidAppSspBitmap

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`long C2xSecCertificateValidAppSspBitmap(long certHdl, dword aid, dword sspLen, byte ssp[], byte msk[], dword checkChain)`

## Description

Validates the **Service Specific Permission** (SSP) bitmask of a certificate.

## Parameters

- **certHdl**: Handle of the certificate to be tested.
- **aid**: Application ID / PSID.
- **sspLen**: Length of the byte arrays ssp and msk (mask).
- **ssp Byte Array**: The SSP to be tested.
- **msk Byte Array**: Mask of the bits in the SSP array to be compared.
- **checkChain**: If set to 1, the whole certificate chain is tested (recommended).

## Return Values

- **kValidOk**: 0x00,
- **kValidError**: 0x01, // unknown / wrong parameter
- **kValidChainIncomplete**: 0x02,
- **kValidChainInvalid**: 0x03, // signature wrong or root not trustworthy
- **kValidConditionNotMet**: 0x04, // country-id or ssp/msk not permitted

## Example

```plaintext
variables
{
  dword myCertHdl;

  struct SspBitmap
  {
    char  name[16];
    dword aid;
    dword len;
    byte  ssp[10];
    byte  msk[10];
    byte  chain;
  };

  struct SspBitmap ssp =
  {
    "CAM",
    0x24,
    3,
    { 0x01, 0x02, 0x00 },
    { 0xff, 0x02, 0x00 },
    1
  };
}

on start
{
  myCertHdl = C2xSecCertificateGetHandle("MyCert");

  write("SSP %s: %d", ssp.name,
    C2xSecCertificateValidAppSspBitmap(myCertHdl, ssp.aid,
    ssp.len, ssp.ssp, ssp.msk, ssp.chain)) ;
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)