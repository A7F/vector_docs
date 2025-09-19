[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetInterFrameSpace.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetInterframeSpace

# linSetInterframeSpace

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```
dword linSetInterframeSpace(dword bitTimes);
```

## Description

This function sets the minimum inter-frame space. With this function it is possible to change the inter-frame space for all frames. The inter-frame space is the time from the end of the frame until start of the next frame. By default the minimum inter-frame space is 0.

**Note**: If the LIN hardware is not in Master mode calling this function will have no effect. If large inter-frame space is set, the schedule slots time may be affected.

## Parameters

- **bitTimes**: Length of the inter-frame space to set [in bit times].  
  Value range: 0..255

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```c
on key 's'
{
    if (linSetInterframeSpace (200) != 0)
    {
        // from now on inter-frame space is minimum 200 bit times
        ...
    }
}
```

[linSetGlobalInterByteSpace](CAPLfunctionLINSetGlobalInterByteSpace.md) • [linSetInterByteSpace](CAPLfunctionLINSetInterByteSpace.md) • [linSetInterByteSpaces](CAPLfunctionLINSetInterByteSpaces.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
