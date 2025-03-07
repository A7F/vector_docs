[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTPktSetTraceColors.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md#TraceHighlighting) » mostPktSetTraceColors

# mostPktSetTraceColors

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
mostPktSetTraceColors(long font, long bkgnd);
```

## Description

Sets the text and background color for displaying the MOST event in the Trace Window. The [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) function can be used for the colors.

**Note**

- This function can only be used in Measurement Setup and is only applied to the Trace Window.
- The setting of colors with this function has a higher priority than the color settings for events in the Trace Window.

## Parameters

- **font**: Font color (RGB value)
- **bkgnd**: Background color (RGB value)

## Return Values

- **0**: OK
- **-1**: Invalid RGB value of a color.

## Example

```plaintext
OnMostPkt (long  pktlen) 
{
    mostPktSetTraceColors(makeRGB(0, 0, 0), makeRGB(255, 0, 0) );
    outputMostPktThis(); // Forwards this packet to the node in the Measurement Setup
}
```

[traceSetEventColors](../../Other/Functions/CAPLfunctionTraceSetEventColors.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)