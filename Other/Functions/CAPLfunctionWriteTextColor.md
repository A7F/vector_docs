[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteTextColor.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeTextColor

# writeTextColor

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeTextColor(dword sink, dword red, dword green, dword blue);
```

## Description

Sets the color for text of the specified page in the Write Window.

You can use the following constants for the target identifier:

```plaintext
// write sinks
dword WRITE_SYSTEM = 0;
dword WRITE_CAPL = 1;
```

In addition, you can use one of the target identifiers returned by the function [writeCreate](CAPLfunctionWriteCreate.md).

The color settings have also an effect on the **All** tab of the Write Window.

## Parameters

- **sink**: The target identifier of the page on which the color settings should have an effect.
- **red**: Specifies the intensity of the red color.
- **green**: Specifies the intensity of the green color.
- **blue**: Specifies the intensity of the blue color.

## Return Values

—

## Example

```plaintext
WriteTextColor(0, 255, 0, 0);
WriteLineEx(0, 1, "This is red text");

WriteTextBkgColor(0, 0, 255, 0);
WriteLineEx(0, 1, "This is red text with green background");

WriteTextColor(0, 0, 0, 0);
WriteTextBkgColor(0, 255, 255, 255);
WriteLineEx(0, 1, "This is black text with white background");
```

[write](CAPLfunctionWrite.md) • [writeCreate](CAPLfunctionWriteCreate.md) • [writeClear](CAPLfunctionWriteClear.md) • [writeDestroy](CAPLfunctionWriteDestroy.md) • [writeEx](CAPLfunctionWriteEx.md) • [writeLineEx](CAPLfunctionWriteLineEx.md) • [writeTextBkgColor](CAPLfunctionWriteTextBkgColor.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
