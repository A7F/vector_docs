[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapObjectSize.md)

**CAPL Functions** » **Map Window API** » **SetMapObjectSize**

# SetMapObjectSize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectSize( long handle, float size ); // form 1
long SetMapObjectSize( long handle, float width, float height ); // form 2
```

## Description

Sets either the size (form 1) or the height and width (form 2) of a map object.

## Parameters

- **handle**: Reference of the map object.
- **size**: Size of the map object in meters.
- **width**: Width of the map object in meters.
- **height**: Height of the map object in meters.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md).

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
