[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsSetsDocAnId.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSetSdoCANid

# coTfsSetSdoCANid

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetSdoCANid( dword sdoClnRxId, dword sdoClnTxId );
```

## Description

With this function the internal CAN identifiers to be used for the SDO tests are set. **All** test functions, which uses SDO access, will use the specified identifiers. This setting will override the application profile specific SDO id settings.

## Parameters

- **sdoClnRxId**: CAN-ID for receive SDOs.
- **sdoClnTxId**: CAN-ID for send SDOs.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetSdoCANid(0x580, 0x602); // set internal CAN-ID for Rx SDOs to 0x580 and for Tx SDOs to 0x602
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)