[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MapWindowAPI/Functions/CAPLfunctionDrawMapObject.md)

**CAPL Functions** » [Map Window API](../CAPLfunctionMapWindowAPI.md) » DrawMapObject

# DrawMapObject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long DrawMapObject( long handle );
```

## Description

Draws a map object in the Map Window with the configured parameters. Function must be called to trigger a repaint, if parameters have been changed.

## Parameters

- **handle**: Reference of the map object

## Return Values

- **0**: success
- **1**: invalid handle

## Example

See [Map Window API example](../CAPLfunctionMapWindowAPI.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)