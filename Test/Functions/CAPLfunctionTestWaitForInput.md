# TestWaitForInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForInput(long handle); // form 1`
- `long TestWaitForInput(long handle, dword timeout); // form 2`
- `long TestWaitForInput(long handle, dword timeout, dword defaultIndex); // form 3`

## Description

After you have created a value table or range dialog use this function to open the dialog.

## Parameters

- **Handle**: The handle of the dialog.
- **DefaultIndex**: The index of the value is marked on dialog opening.
- **Timeout**: Optional timeout for the dialog in ms. Transmission of 0: no timeout controlling.

## Return Values

- **1**: Dialog was closed by clicking the button **[Ok]** (successful call)
- **2**: Dialog was closed by clicking the button **[Cancel]**

## Example

```c
handle = TestCreateValueInputTable("Test Text", "Test Caption", "Test Value Input Table Timeout");
TestAddValueTableEntry(handle, 9);
return = TestWaitForInput(handle, 5000);
write("Result: %f", TestGetValueInput());
```
