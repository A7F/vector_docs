[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapObjectLineColor.md)

**CAPL Functions** » **Map Window API** » **SetMapObjectLineColor**

# SetMapObjectLineColor

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectLineColor( long handle, float lineColor );
```

## Description

Sets the line color of a map object.

## Parameters

- **handle**: Reference of the map object
- **lineColor**: RGB color value (e.g. calculated by [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md), default: 0)

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

## Return Values

0 if success, else the set went wrong

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)