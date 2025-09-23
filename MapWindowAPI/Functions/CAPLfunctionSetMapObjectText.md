# SetMapObjectText

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectText( long handle, char text[] ); // form 1
long SetMapObjectText( long handle, char formattedText[], float value ); // form 2
```

## Description

Sets text (form 1) or formatted text (form 2) for a map object of the type text.

**Note makeRGB**

- Up to and including CANoe DE product version 12.0 SP2, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returned the blue value in the second byte and the red value in the fourth byte. Functions that received this value as a parameter interpreted this exchange so that the color was displayed correctly.
- From CANoe DE product 12.0 SP3, the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) returns the color values in the correct order. Functions that have received this value as a parameter have also been adjusted to display the correct color again.
- Existing programs only need to be adapted if you have not used the function [makeRGB](../../Other/Functions/CAPLfunctionMakeRGB.md) but you have passed the color hard coded.

## Parameters

- **handle**: Reference of the map object.
- **text**: Text which should be displayed.
- **formattedText**: Text with a placeholder for a variable which should be displayed.
- **value**: Variable which should be displayed in the text.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

```plaintext
void DrawTextObject()
{
  long handle;
  float timeRemaining = 5.8;

  handle = CreateMapObject( 8 );

  // set position: Motorstraße/Hemminger Straße, D-70499 Stuttgart
  SetMapObjectPosition(handle, 48.825230, 9.095580);
  SetMapObjectText(handle, "Traffic Light: time remaining %5.1f s", timeRemaining);
  SetMapObjectFillColor(handle, makeRGB(0, 0, 0));
  DrawMapObject(handle);
}
```
