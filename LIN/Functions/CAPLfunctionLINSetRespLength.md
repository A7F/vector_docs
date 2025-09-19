[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetRespLength.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetRespLength

# linSetRespLength

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linSetRespLength(long frameID, long numberOfBytes);
```

## Description

This function can be used to configure how many data bytes of the frame response should be sent. The frame’s length is not changed by this function.

To send a correct response the **numberOfBytes** should be set equal to DLC+1 i.e for the frame data bytes and their checksum.

If the **numberOfBytes** is set to a value larger than DLC + 1, then a complete response is also sent.

If the **numberOfBytes** is set to a value smaller than DLC+1, then a receiving error will occur or if numberOfBytes = 0 a transmission error.

**Note**: This function can be used to simulate collisions during sending of a frame response e.g. after receiving an event triggered frame.

## Parameters

- **frameID**: Identifier of the LIN frame to be configured.  
  Value range: 0…63

- **numberOfBytes**: Number of bytes to be sent in the frame response (including checksum).  
  Value range: 0..DLC+1

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
linFrame MotorControl frameMotorControl;
...
if (linSetRespLength (frameMotorControl.ID, frameMotorControl.DLC) != 0) {
   // from now on a receive error notified for the MotorControl frame
   ...
}
if (linSetRespLength (frameMotorControl.ID, 0) != 0)
{
   // from now on a transmission error notified for the MotorControl frame
   ...
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
