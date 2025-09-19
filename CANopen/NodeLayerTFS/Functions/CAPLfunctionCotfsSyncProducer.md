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
