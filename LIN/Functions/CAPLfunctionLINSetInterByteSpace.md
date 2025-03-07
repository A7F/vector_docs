[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetInterByteSpace.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetInterByteSpace

# linSetInterByteSpace

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linSetInterByteSpace (long frameID, long index, dword sixteenthBits);
```

## Description

With this function it is possible to set an inter-byte space for a specified frame and a specified byte field. The byte field may belong to the frame header as well as to the frame response.

Inter-byte space is the period between the end of the stop bit of the preceding byte and the start bit of the following byte.

By default, the inter-byte space is 0.

## Parameters

- **frameID**: LIN frame identifier whose inter-byte space should be changed.  
  Value range: 0…63

- **index**: Index of the byte field, before which the inter-byte space should be inserted.  
  Value range: 0..N+1, where N=frame length  
  0: Inter-byte is inserted between the Synch byte and the Identifier byte.  
  1: Inter-byte is inserted before the first data byte.  
  N+1: Inter-byte is inserted before the Checksum byte.

- **sixteenthBits**: Length of the inter-byte space to set [in units of 1/16th of bit time].  
  Value range: 0..65535. This corresponds to 0..4095.93 bit times.  
  For a LIN standard compliance: The maximum space between the bytes cannot exceed 40% duration compared to nominal transmission time.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```c
on key 's'
{
    if ( linSetInterByteSpace(0x33, 9, 32) != 0)
    {
        // from now on for frame ID=0x33 the inter-byte space 
        // between last data byte field and Checksum byte is 2 bit times
        ...
    }
}
```

[linSetGlobalInterByteSpace](CAPLfunctionLINSetGlobalInterByteSpace.md) • [linSetInterframeSpace](CAPLfunctionLINSetInterFrameSpace.md) • [linSetInterByteSpaces](CAPLfunctionLINSetInterByteSpaces.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)