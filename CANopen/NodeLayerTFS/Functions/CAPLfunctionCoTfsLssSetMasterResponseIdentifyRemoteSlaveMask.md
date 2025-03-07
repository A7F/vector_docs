[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSetMasterResponseIdentifyRemoteSlaveMask.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsLssSetMasterResponseIdentifyRemoteSlaveMask**

# coTfsLssSetMasterResponseIdentifyRemoteSlaveMask (Level 2)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSetMasterResponseIdentifyRemoteSlaveMask( dword vendorIdMask, dword productCodeMask, dword revisionNoLowMask, dword revisionNoHighMask, dword serialNoLowMask, dword serialNoHighMask );
```

## Description

This function sets the masks for the parameters of function [coTfsLssAddMasterResponseIdentifyRemoteSlave](CAPLfunctionCoTfsLssAddMasterResponseIdentifyRemoteSlave.md) and has to be called before that function.

## Parameters

- **vendorIdMask**: Mask for vendor-ID parameter; set bits are compared, not set bits are not compared.
- **productCodeMask**: Mask for product code parameter; set bits are compared, not set bits are not compared.
- **revisionNoLowMask**: Mask for low boundary of revision number parameter; set bits are compared, not set bits are not compared.
- **revisionNoHighMask**: Mask for high boundary of revision number parameter; set bits are compared, not set bits are not compared.
- **serialNoLowMask**: Mask for low boundary of serial number parameter; set bits are compared, not set bits are not compared.
- **serialNoHighMask**: Mask for high boundary of serial number parameter; set bits are compared, not set bits are not compared.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)