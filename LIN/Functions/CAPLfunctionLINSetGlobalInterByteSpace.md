[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetGlobalInterByteSpace.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetGlobalInterByteSpace

# linSetGlobalInterByteSpace

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linSetGlobalInterByteSpace(dword sixteenthBits);
```

## Description

With this function, it is possible to change the inter-byte space for all frame responses. Inter-byte space is the period between the end of the stop bit of the preceding byte and the start bit of the following byte.

By default, the inter-byte space is 0.

**Note:** This function affects only frames published by the modeled LIN node(s), i.e., frames sent not by external hardware.

## Parameters

- **sixteenthBits**: Length of the inter-byte space to set [in units of 1/16th of bit time].
  - Value range: 0..65535. This corresponds to 0..4095.93 bit times.
  - For LIN standard compliance: The maximum space between the bytes cannot exceed 40% duration compared to nominal transmission time.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 's'
{
    if ( linSetGlobalInterByteSpace(16) != 0)
    {
        // from now on the inter-byte space in all frame responses is 1 bit time
        ...
    }
}
```

[linSetInterByteSpace](CAPLfunctionLINSetInterByteSpace.md) • [linSetInterByteSpaces](CAPLfunctionLINSetInterByteSpaces.md) • [linSetInterframeSpace](CAPLfunctionLINSetInterFrameSpace.md)
