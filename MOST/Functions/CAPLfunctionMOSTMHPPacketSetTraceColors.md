[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTMHPPacketSetTraceColors.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md#TraceHighlighting) » mostMHPPacketSetTraceColors

# mostMHPPacketSetTraceColors

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`mostMHPPacketSetTraceColors(long font, long bkgnd);`

## Description

Sets the text and background color for displaying the MOST event in the Trace Window. The [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) function can be used for the colors.

**Note**

- This function can only be used in Measurement Setup and is only applied to the Trace Window.
- The setting of colors with this function has a higher priority than the color settings for events in the Trace Window.

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

## Parameters

- **font**: Font color (RGB value)
- **bkgnd**: Background color (RGB value)

## Return Values

- **0**: OK
- **-1**: Invalid RGB value of a color.

## Example

```plaintext
OnMostMHPPacket (long  sourceDevID, long destDevID, long fBlockID, long instID, long functionID, long  opType)
{
   mostMHPPacketSetTraceColors(makeRGB(0, 0, 0), makeRGB(255, 0, 0) );
   return 1; // Forward the MHPPacket to the next node in the Measurement Setup
}
```

[traceSetEventColors](../../Other/Functions/CAPLfunctionTraceSetEventColors.md)
