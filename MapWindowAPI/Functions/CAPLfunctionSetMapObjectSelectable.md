# SetMapObjectSelectable

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionSetMapObjectSelectable.md)

**CAPL Functions** » **Map Window API** » SetMapObjectSelectable

## Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetMapObjectSelectable( long handle, long selectable );
```

## Description

Defines if a map object will raise the callback [OnMapObjectClick](../Callbacks/CAPLfunctionOnMapObjectClick.md) when it is clicked with the mouse cursor.

## Parameters

- **handle**: Handle of the map object.
- **selectable**: 1 = true, 0 = false.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
