[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsLssSendIdentifyRemoteSlaveSeq.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsLssSendIdentifyRemoteSlaveSequence

# coTfsLssSendIdentifyRemoteSlaveSequence (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendIdentifyRemoteSlaveSequence( dword vendorId, dword productCode, dword revNoLowBound, dword revNoHighBound, dword serialNoLowBound, dword serialNoHighBound );
```

## Description

This function sends a **LSS identify remote slave** sequence.

## Parameters

- **vendorId**: Vendor-ID
- **productCode**: Product code
- **revNoLowBound**: Low boundary of the revision number.
- **revNoHighBound**: High boundary of the revision number.
- **serialNoLowBound**: Low boundary of the serial number.
- **serialNoHighBound**: High boundary of the serial number.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* sends LSS identify remote slave sequence */

if (coTfsLssSendIdentifyRemoteSlaveSequence( 0x1234, 0x43214321, 0, 0xFFFFFFFF, 0, 1000 ) == 1) {
  /* received LSS identify remote slave sequence, sent response with selected parameters */
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)