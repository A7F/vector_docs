[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetInterByteSpaces.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetInterByteSpaces

# linSetInterByteSpaces

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linSetInterByteSpaces(dword arrayOfSixteenthBits[]);` // form 1
- `dword linSetInterByteSpaces(long frameID, dword arrayOfSixteenthBits[]);` // form 2

## Description

With the first function, it is possible to set the inter-byte spaces [in bit times] for all data byte fields of all published frames (except for diagnostic frame 0x3D) of the calling LIN Slave node.

With the second function, it is possible to set the inter-byte spaces [in bit times] for all data byte fields of a specified frame.

Inter-byte space is the period between the end of the stop bit of the preceding byte and the start bit of the following byte.

By default, the inter-byte space between all byte fields is 0.

## Parameters

- **frameID**: LIN frame identifier whose inter-byte space should be changed  
  Value range: 0 .. 63

- **arrayOfSixteenthBits[]**: Array of 9 elements for inter-byte space lengths, when the length of the inter-byte space is in units of 1/16th of bit time.  
  The first element specifies the inter-byte space before the first data byte. It continues in the same manner until Checksum byte. All not used elements must be set to 0.  
  Value range for inter-byte lengths: 0..65535. This corresponds to 0..4095.93 bit times.  
  For a LIN standard compliance: The maximum space between the bytes cannot exceed 40% duration compared to nominal transmission time.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
on key 's'
{
    int index;
    dword arrayOfSixteenthBits[9];
    linFrame MotorControl frameMotorControl;
    for (index=0; index < 9; ++index)
    {
        if (index <= frameMotorControl.DLC+1) {
            // for all valid data bytes and checksum byte set inter-byte space to 2 bit times
            arrayOfSixteenthBits[index] = 32;
        }
        else {
            // initialize unused array elements
            arrayOfSixteenthBits[index] = 0;
        }
    }
    if (linSetInterByteSpaces(0x33, arrayOfSixteenthBits) != 0) {
        // the inter-byte spaces successfully set
        ...
    }
}
```

[linSetGlobalInterByteSpace](CAPLfunctionLINSetGlobalInterByteSpace.md) • [linSetInterByteSpace](CAPLfunctionLINSetInterByteSpace.md) • [linSetInterframeSpace](CAPLfunctionLINSetInterFrameSpace.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
