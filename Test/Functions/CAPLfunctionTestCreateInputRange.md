# TestCreateInputRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestCreateStringInputRange(char text[], char caption[], char info[]);`
- `TestCreateValueInputRange(char text[], char caption[], char info[]);`
- `TestCreateByteInputRange(char text[], char caption[], char info[]);`

## Description

This function creates an input dialog. For adding a new range to define the input use the command `TestAddRange`. After all ranges are added the dialog can be opened by the command `TestWaitForInput`.

## Parameters

- **Text**: Text to be displayed in the entry dialog.
- **Caption**: The title of the dialog.
- **Info**: Further information to be shown.

## Return Values

The handle of the dialog.

## Example

```plaintext
handle = TestCreateStringInputRange("Test Text", "Test Caption", "Test String Input Range Timeout");
TestAddRange(handle, 0, 5);
TestWaitForInput(handle, 5000);
TestGetStringInput(resultStr, elcount(resultStr));

handle = TestCreateValueInputRange("Test Text", "Test Caption", "Test Value Input Range Timeout");
TestAddRange(handle, 0, 5);
TestWaitForInput(handle, 5000);

handle = TestCreateByteInputRange("Test Text", "Test Caption", "Test Byte Input Range Timeout");
TestAddRange(handle, 0, 5);
TestWaitForInput(handle, 5000);
TestGetByteInput(resultByte, elcount(resultByte));
```
