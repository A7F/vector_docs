[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestAddRange.md)

# TestAddRange

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestAddRange

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`TestAddRange(long handle, double minValue, double maxValue);`

## Description

This function adds a new range that is allowed for dialog input. This can be a minimum/maximum for a numerical value or a minimum/maximum length of a string or byte array.

## Parameters

- **Handle**: The handle of the dialog.
- **minValue**: The minimum of the input.
- **maxValue**: The maximum of the input.

## Return Values

—

## Example

```plaintext
handle = TestCreateValueInputRange("Test Text", "Test Caption", "Test Value Input Range Timeout");
TestAddRange(handle, 0, 5);
TestWaitForInput(handle, 5000);
write("Result: %f", TestGetValueInput());
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
