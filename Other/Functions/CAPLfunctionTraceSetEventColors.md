[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTraceSetEventColors.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » traceSetEventColors

# traceSetEventColors

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long traceSetEventColors(message msg, dword font, dword bkgnd); // form 1`
- `long traceSetEventColors(errorFrame msg, dword font, dword bkgnd) // form 2`
- `long traceSetEventColors(pg msg, dword font, dword bkgnd) // form 3`
- `long traceSetEventColors(linFrame msg, dword font, dword bkgnd) // form 4`
- `long traceSetEventColors(mostRawMessage msg, dword font, dword bkgnd) // form 5`
- `long traceSetEventColors(mostMessage msg, dword font, dword bkgnd) // form 6`
- `long traceSetEventColors(mostAmsMessage msg, dword font, dword bkgnd) // form 7`
- `long traceSetEventColors(frFrame msg, dword font, dword bkgnd) // form 8`
- `long traceSetEventColors(frError msg, dword font, dword bkgnd) // form 9`
- `long traceSetEventColors(FrFrameError msg, dword font, dword bkgnd) // form 10`
- `long traceSetEventColors(FrNullFrame msg, dword font, dword bkgnd) // form 11`
- `long traceSetEventColors(FrPDU msg, dword font, dword bkgnd) // form 12`
- `long traceSetEventColors(FrPOCState msg, dword font, dword bkgnd) // form 13`
- `long traceSetEventColors(FrSlot msg, dword font, dword bkgnd) // form 14`
- `long traceSetEventColors(FrStartCycle msg, dword font, dword bkgnd) // form 15`
- `long traceSetEventColors(FrSymbol msg, dword font, dword bkgnd) // form 16`
- `long traceSetEventColors(ethernetPacket msg, dword font, dword bkgnd) // form 17`
- `long traceSetEventColors(ethernetErrorPacket msg, dword font, dword bkgnd) // form 18`

## Description

Sets the text and background color for displaying **msg** in the Trace Window. The [makeRGB](CAPLfunctionMakeRGB.md) function can be used for the colors.

**Note**

- This function can only be used in Measurement Setup and is only applied to the Trace Window.
- The setting of colors with this function has a higher priority than the color settings for events in the Trace Window.

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

## Parameters

- **msg**: Variable type: message, errorFrame, pg, linFrame, mostRawMessage, mostMessage, mostAmsMessage, frFrame, frError, frameError, nullFrame, pdu, pocState, slot, symbol, startCycle
- **font**: Font color (RGB value)
- **bkgnd**: Background color (RGB value)

## Return Values

- **0**: OK
- **-1**: Invalid RGB value of a color.

## Example

```plaintext
on message *
{
   traceSetEventColors(this, makeRGB(0x00, 0xFF, 0xFF), makeRGB(0x00, 0x00, 0x00));
   output(this);
}

on message *
{
   message * msg;
   msg = this;
   traceSetEventColors(msg, makeRGB(0x00, 0xFF, 0xFF), makeRGB(0x00, 0x00, 0x00));
   output(msg);
}
```

[MOST Trace Highlighting](../../MOST/CAPLfunctionsMOSTOverview.md#TraceHighlighting)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)