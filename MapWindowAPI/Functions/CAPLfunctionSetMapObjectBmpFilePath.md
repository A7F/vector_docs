[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapObjectBmpFilePath.md)

[CAPL Functions](../../CAPLfunctions.md) » [Map Window API](../CAPLfunctionMapWindowAPI.md) » SetMapObjectBmpFilePath

# SetMapObjectBmpFilePath

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectBmpFilePath( long handle, char filePath[] );
```

## Description

Sets the file path to a bitmap for a map object of the type bitmap. For transparency pure white color (RGB 255, 255, 255) is used.

## Parameters

- **handle**: Reference of the map object.
- **filePath**: Path of the bitmap file. You can set an absolute path (e.g. "C:\myCANoeConfig\bmp\circles.bmp") or a relative path (e.g. "bmp\circles.bmp"). If the relative option is used, the path is seen relative to the location of the CANoe configuration. If the bitmap file could not be found or load, a default bitmap is displayed in the Map Window.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

```plaintext
void DrawBitmapObject()
{
  long handle;

  // both file paths lead to the same bitmap
  char filePathRelative[30] = "bmp\\TrafficLight.bmp";
  char filePathAbsolute[50] = "C:\\myCANoeConfig\\bmp\\TrafficLight.bmp";
  handle = CreateMapObject( 7 ); // bitmap

  // set position: Motorstraße/Hemminger Straße, D-70499 Stuttgart
  SetMapObjectPosition(handle, 48.825240, 9.095642);
  SetMapObjectBmpFilePath(handle, filePathRelative);
  SetMapObjectBmpCount(handle, 4);
  SetMapObjectBmpIndex(handle, 1); // green traffic light
  SetMapObjectSize(handle, 1.8, 4.2);
  SetMapObjectHeading(handle, 87);
  DrawMapObject(handle);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
