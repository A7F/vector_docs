[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapObjectFillColor.md)

**CAPL Functions** » **Map Window API** » **SetMapObjectFillColor**

# SetMapObjectFillColor

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectFillColor( long handle, float fillColor );
```

## Description

Sets the fill color of a map object or the text color of a text object.

## Parameters

- **handle**: Reference of the map object.
- **fillColor**:
  - RGB color value (e.g. calculated by [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md)).
  - -1: resets the fill color to transparent (default, except for text objects which use red text color as default).

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
