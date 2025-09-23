[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetExpectedRespLength.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linSetExpectedRespLength

# linSetExpectedRespLength

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long linSetExpectedRespLength(long frameID, long numberOfBytes);
```

## Description

This function can be used to configure how many data bytes of the frame response will be expected on reception. Reception of a LIN frame with a number of data bytes deviant from the expected number of bytes will lead to either a CRC error (if more bytes were received than expected) or a RcvError (if less bytes were received than expected). The actual length of frames transmitted on the bus will remain unchanged.

**Note**: A channel receiving a LIN response can be reconfigured, using `linSetExpectedRespLength`, to accept a LIN frame with a differing DLC from what was initially configured (e.g. by the LDF database).

To change the maximum number of bytes transmitted, use [linSetRespLength](CAPLfunctionLINSetRespLength.md). `linSetRespLength` and `linSetExpectedRespLength` cannot be used together to correctly reconfigure a LIN frame to be sent with a different length. Use **output(linFrame)** for this purpose.

**Note**: Use this function (as well as [linSetRespLength](CAPLfunctionLINSetRespLength.md)) with care, because it is possible to get the LIN interface stuck in configurations which aren’t easy to resolve. It’s not recommended to use `linSetRespLength` and `linSetExpectedRespLength` in combination on the same channel.

## Parameters

- **frameID**: Identifier of the LIN frame to be configured.  
  Value range: 0…63

- **numberOfBytes**: Number of expected data bytes (excluding the CRC byte).  
  Value range: 1..8

## Return Values

On success, returns 1, otherwise 0.

## Example

—
