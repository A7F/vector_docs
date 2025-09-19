[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Callbacks/CAPLfunctionOnMapObjectClick.md)

**CAPL Functions** » **Map Window API** » **OnMapObjectClick**

# OnMapObjectClick

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`OnMapObjectClick ( long handle );`

## Description

Function is called when a map object is clicked. It is only raised for map objects that are defined as selectable using the function [SetMapObjectSelectable](../Functions/CAPLfunctionSetMapObjectSelectable.md).

## Parameters

- **handle**: Handle of the map object.

## Return Values

- **0**: Success
- **≠0**: The set went wrong.

## Example

```plaintext
OnMapObjectClick(long handle)
{
  // refer to information of a map object here that was stored before for the corresponding handle
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
