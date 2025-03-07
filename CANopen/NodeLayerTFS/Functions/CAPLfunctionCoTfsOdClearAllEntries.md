[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsOdClearAllEntries.md)

[CAPL Functions](../../../CAPLfunctions.md) » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsODClearAllEntries

# coTfsODClearAllEntries (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsODClearAllEntries( void );
```

## Description

The function deletes all objects of the internal test object list, which is used by [coTfsODChk](CAPLfunctionCoTfsOdChk.md) and [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsODAddEntry](CAPLfunctionCoTfsOdAddEntry.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)