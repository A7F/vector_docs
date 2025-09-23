# TestAddValueTableEntry

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestAddStringTableEntry(long handle, char[] value);`
- `TestAddStringTableEntry(long handle, char[] value, dword isDefaultIndex);`
- `TestAddValueTableEntry(long handle, double value);`
- `TestAddValueTableEntry(long handle, double value, dword isDefaultIndex);`

## Description

This functions adds a new value table entry.

## Parameters

- **Handle**: The handle of the dialog.
- **Value**: The value should be added to the dialog table.
- **IsDefaultIndex**: If isDefaultIndex = 0 this Entry will be set as default.

## Return Values

—

## Example

```plaintext
handle = TestCreateStringInputTable("Test Text", "Test Caption", "Test String Input Table Timeout");
TestAddStringTableEntry(handle, "Test Entry");
TestWaitForInput(handle, 5000);
TestGetStringInput(resultStr, elcount(resultStr));

handle = TestCreateValueInputTable("Test Text", "Test Caption", "Test Value Input Table Timeout");
TestAddValueTableEntry(handle, 9);
TestWaitForInput(handle, 5000);
write("Result: %f", TestGetValueInput());
```
