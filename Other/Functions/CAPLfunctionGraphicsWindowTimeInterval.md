[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGraphicsWindowTimeInterval.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » graphicsWindowTimeInterval

# graphicsWindowTimeInterval

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void graphicsWindowTimeInterval(char[] windowName, int64 from, int64 to);
```

## Description

Sets the time interval that will be displayed in a CANoe DE product [Graphics Window](../../../CANoeCANalyzer/Windows/Graphics/GraphicsWindow.md).

## Parameters

- **windowName**: The name of the Graphics Window.
- **from / to**: Defines the time interval in [ns]. The time can be retrieved by [timeNowInt64](CAPLfunctionTimeNowNS.md).

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
