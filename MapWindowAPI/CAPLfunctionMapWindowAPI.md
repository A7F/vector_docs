[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/CAPLfunctionMapWindowAPI.md)

[CAPL Functions](../CAPLfunctions.md) » Map Window API » Map Window API

# Map Window API

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

Initially the object type is defined by means of [CreateMapObject](Functions/CAPLfunctionCreateMapObject.md). In general the following functions are available independent of the object type:

- [SetMapObjectPosition](Functions/CAPLfunctionSetMapObjectPosition.md)
- [DrawMapObject](Functions/CAPLfunctionDrawMapObject.md)
- [DeleteMapObject](Functions/CAPLfunctionDeleteMapObject.md)
- [SetMapPosition](Functions/CAPLfunctionSetMapPosition.md)

In addition to this dependent on the object type the following functions can be used:

- **AddMapPolylinePoint**: Polyline
- **ClearMapPolyline**: Polyline
- **OnStationClick**: —
- **OnMapObjectClick**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Bitmap, Text, Vehicle, Polyline
- **SetMapObjectBmpCount**: Bitmap
- **SetMapObjectBmpFilePath**: Bitmap
- **SetMapObjectBmpIndex**: Bitmap
- **SetMapObjectFillColor**: Square, Rectangle, Ellipse, Triangle, Text, Vehicle
- **SetMapObjectHeading**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Text, Vehicle
- **SetMapObjectLineColor**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Vehicle, Polyline
- **SetMapObjectSelectable**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Bitmap, Text, Vehicle, Polyline
- **SetMapObjectPenWidth**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Vehicle, Polyline
- **SetMapObjectSize**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Text, Vehicle
- **SetMapObjectText**: Text
- **SetMapObjectVisible**: Square, Rectangle, Ellipse, Cross, Triangle, Line, Bitmap, Text, Vehicle, Polyline

**Example**

```plaintext
variables
{
  enum mapObjectType { Square = 1, Rectangle = 2, Ellipse = 3, Cross = 4, Triangle = 5, Line = 6, Bitmap = 7, Text = 8, Vehicle = 9, Polyline = 10};
  long gHandle;
}

on start
{
  // init object
  gHandle = CreateMapObject( Rectangle );

  // set position: Ingersheimer Straße 24, D-70499 Stuttgart
  SetMapObjectPosition(gHandle, 48.824892, 9.094265);

  // optional settings
  SetMapObjectHeading(gHandle, 359);
  SetMapObjectSize(gHandle, 2, 4.5);
  SetMapObjectFillColor(gHandle, makeRGB(183, 0, 50));
  SetMapObjectLineColor(gHandle, makeRGB(76, 76, 76));
  SetMapObjectPenWidth(gHandle, 3);

  // draw object
  DrawMapObject(gHandle);
}

on key 'd'
{
  // delete object
  DeleteMapObject(gHandle);
}
```

[Option Car2x](../../CANoeCANalyzer/Car2x/Car2x.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)