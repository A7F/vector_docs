[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestCreateInputTable.md)

## CAPL Functions » Test Feature Set » TestCreateStringInputTable, TestCreateValueInputTable

### TestCreateStringInputTable, TestCreateValueInputTable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

- `TestCreateStringInputTable(char text[], char caption[], char info[]);`
- `TestCreateValueInputTable(char text[], cahr caption[], char info[]);`

### Description

This function creates a selection dialog. To add a value table entry, use the command `TestAddValueTableEntry` or `TestAddStringTableEntry`. After all entries are added the dialog can be opened by the command `TestWaitForInput`.

### Parameters

- **Text**: Text to be displayed in the entry dialog
- **Caption**: The title of the dialog.
- **Info**: Further information to be shown.

### Return Values

The handle of the dialog.

### Example

```c
handle = TestCreateStringInputTable("Test Text", "Test Caption", "Test String Input Table Timeout");
TestAddStringTableEntry(handle, "Test Entry");
TestWaitForInput(handle, 5000);
TestGetStringInput(resultStr, elcount(resultStr));

handle = TestCreateValueInputTable("Test Text", "Test Caption", "Test Value Input Table Timeout");
TestAddValueTableEntry(handle, 9);
TestWaitForInput(handle, 5000);
write("Result: %f", TestGetValueInput());
```
