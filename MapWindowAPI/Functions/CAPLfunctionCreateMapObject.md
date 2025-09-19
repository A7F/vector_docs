[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionCreateMapObject.md)

**CAPL Functions** » **Map Window API** » **CreateMapObject**

# CreateMapObject

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long CreateMapObject( long objectType );
```

## Description

Initializes a map object to be drawn in the Map Window.

## Parameters

- **objectType**: Figure to be drawn in the Map Window:
  - 1: Square
  - 2: Rectangle
  - 3: Ellipse
  - 4: Cross
  - 5: Triangle
  - 6: Line
  - 7: Bitmap
  - 8: Text
  - 9: Vehicle

## Return Values

Handle of the created map object.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
