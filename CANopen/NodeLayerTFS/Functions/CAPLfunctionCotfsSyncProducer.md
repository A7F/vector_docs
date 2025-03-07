[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCotfsSyncProducer.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsSyncProducer

# coTfsSyncProducer (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSyncProducer( void );
```

## Description

The call of this function starts a sync test that lasts 5 s. The sync producer in the DUT generates a sync message every 100 ms. The tolerance is ±10 ms. At the end of the test, the successful switch-off of the sync producer is checked.

This test does not support devices, which use the sync counter. Use the function [coTfsSyncProducerDetail](CAPLfunctionCoTfsSyncProducerDetail.md) instead.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSyncProducer();
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)