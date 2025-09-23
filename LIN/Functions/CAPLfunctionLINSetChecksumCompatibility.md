[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetChecksumCompatibility.md)

**CAPL Functions** » **LIN** » **linSetChecksumCompatibility**

# linSetChecksumCompatibility

[Feature availabilty for your product](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long linSetChecksumCompatibility(long channel); // form 1`
- `long linSetChecksumCompatibility(); // form 2`

## Description

Switches the checksum calculation model of all frames that have at least one subscribed LIN 1.x node to the classic model.

**Note**: This function may only be called in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md).

## Parameters

- **channel**: The number of the LIN channel for which the checksum compatibility should be enabled.  
  Value range: 1..32

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on prestart
{
  /*send and receive all frames that are received by at least one Lin 1.x node using the classic checksum model.*/
  linSetChecksumCompatibility();
}

on prestart
{
  /*send and receive all frames on channel 1 that are received by at least one Lin 1.x node using the classic checksum model.*/
  linSetChecksumCompatibility(1);
}
```

[linGetChecksum](CAPLfunctionLINGetChecksum.md) • [linSetChecksumModel](CAPLfunctionLINSetChecksumModel.md)
