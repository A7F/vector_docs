# TestWaitForValueInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForValueInput (char aQuery []); // form 1`
- `long TestWaitForValueInput (char aQuery [], dword aTimeout); // form 2`
- `long TestWaitForValueInput(char text[], char caption[], char info[]); // form 3`
- `long TestWaitForValueInput(char text[], char caption[], char info[], dword timeout); // form 4`

## Description

It creates a dialog which displays the transferred string. The tester can enter a number in this dialog. The number can be entered in decimal as well as hexadecimal form. Only characters allowed for numeric values are allowed. Upon closing the dialog, an additional check of the number entered is performed. If the entry cannot be converted to a valid number, an error message is generated and the dialog is exited. The entry can be queried after a successful call with the commands [TestGetValueInput](CAPLfunctionTestGetValueInput.md) (number value) and [TestGetStringInput](CAPLfunctionTestGetStringInput.md) (entry as String). It is also possible to enter a comment in the dialog which is automatically adopted into the test report.

The first wait function without timeout waits until the confirmation by the tester. If the second wait function is used with the timeout, the dialog is automatically closed after the timeout. Whether the dialog was closed due to a timeout or by the tester, can be determined by using the return value.

The function [TestGetLastWaitResult](CAPLfunctionTestGetLastWaitResult.md) can be queried after calling the return value of the function if no other `TestWaitForValueInput` call occurred in the interim.

Only one dialog is open at a time, even though `TestWaitForValueInput` is called by different test modules.

You can optionally define some default input for the dialog.

## Parameters

- **aQuery**: Text to be displayed in the entry dialog
- **aTimeOut**: Time in milliseconds after which the dialog is to be cancelled.
- **Text**: Text to be displayed in the entry dialog.
- **Caption**: The title of the dialog.
- **Info**: Further information to be shown.
- **Timeout**: Optional timeout for the dialog in ms. Transmission of 0: no timeout controlling.

## Return Values

- **\< 0**: General error, e.g. by calling outside of a test sequence
- **0**: Timeout occurred
- **1**: Dialog was closed by clicking the button **[Ok]** (successful call)
- **2**: Dialog was closed by clicking the button **[Cancel]** (form 3-4)

## Example

**Example 1**

```plaintext
// ask for the test ID and report it in the Write Window
TestWaitForValueInput("Please enter the test ID", 5000);
Write("Test ID = %f", TestGetValueInput());
```

**Example 2**

```plaintext
return = TestWaitForValueInput("Test Text", "Test Caption", "Test Value Input", 0);
write("Result: %f", TestGetValueInput());

return = TestWaitForValueInput("Test Text", "Test Caption", "Test Value Input Timeout", 5000);
write("Result: %f", TestGetValueInput());
```
