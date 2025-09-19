[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetChecksumModel.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetChecksumModel

# linSetChecksumModel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long linSetChecksumModel(long channel, long frameID, long checksumModel); // form 1`
- `long linSetChecksumModel(long frameID, long checksumModel); // form 2`

## Description

Sets the checksum calculation model of a single frame.

**Note**

- This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).
- If the affected LIN channel uses a protocol version that does not support the enhanced checksum model, setting a frame identifier to enhanced checksum model will fail.

## Parameters

- **channel**: The channel for which the checksum model of the frame should be changed. Value range: 1..32
- **frameId**: The unprotected identifier of the frame. Value range: 0 .. 63 (excluding 60 and 61).
- **checksumModel**:
  - Value range: 0..1
  - 0: **classic** (LIN 1.x) checksum model
  - 1: **enhanced** (LIN 2.x) checksum model

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on prestart
{
  /*send and receive the frame with the ID "4" using the classic checksum model*/
  linSetChecksumModel(4,0);
}

on prestart
{
  /*send and receive the frame with the ID "4" on channel 1 using the classic checksum model*/
  linSetChecksumModel(1,4,0);
}
```

[linGetChecksum](CAPLfunctionLINGetChecksum.md) • [linSetChecksumCompatibility](CAPLfunctionLINSetChecksumCompatibility.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
