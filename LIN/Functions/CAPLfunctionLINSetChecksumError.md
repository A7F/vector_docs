[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetChecksumError.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetChecksumError

# linSetChecksumError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linSetChecksumError(long frameId, long activate);
```

## Description

Sets/resets a checksum error of a LIN frame. The activated checksum error is then constant and will not be affected by changes in the frame data.

## Parameters

- **frameId**: LIN frame identifier in the range 0 .. 63.
- **activate**:
  - 0: deactivate checksum error
  - 1: activate checksum error

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

Cause checksum error for all LIN frames on the bus

```plaintext
on linFrame *
{
    linSetChecksumError(this.id, 1);
}
```

[linGetChecksum](CAPLfunctionLINGetChecksum.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
