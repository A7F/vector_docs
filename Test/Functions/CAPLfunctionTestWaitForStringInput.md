[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForStringInput.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForStringInput**

# TestWaitForStringInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForStringInput (char aQuery[]); // form 1`
- `long TestWaitForStringInput (char aQuery[], dword aTimeout); // form 2`
- `long TestWaitForStringInput(char text[], char caption[], char info[], char default[]); // form 3`
- `long TestWaitForStringInput(char text[], char caption[], char info[], char default[], dword timeout); // form 4`
- `long TestWaitForStringInput(char text[], char caption[], char info[], char regEx[], char default[]); // form 5`
- `long TestWaitForStringInput(char text[], char caption[], char info[], char regEx[], char default[], dword timeout); // form 6`

## Description

It creates a dialog which displays the transferred string. The tester can enter a text in this dialog. This entry can be queried with the command [TestGetStringInput](CAPLfunctionTestGetStringInput.md) after a successful call, i.e. with the return value "1". It is also possible to enter a comment in the dialog which is automatically adopted into the test report.

The first wait function without timeout waits until the confirmation by the tester. If the second wait function is used with the timeout, the dialog is automatically closed after the timeout. Whether the dialog was closed due to a timeout or by the tester, can be determined by using the return value.

The function [TestGetLastWaitResult](CAPLfunctionTestGetLastWaitResult.md) can be queried after calling the return value of the function if no other `TestWaitForStringInput` call occurred in the interim.

Only one dialog is open at a time, even though `TestWaitForStringInput` is called by different test modules. You can optionally define some default input for the dialog or a regular expression for checking the input.

## Parameters

- **aQuery**: Text to be displayed in the entry dialog.
- **aTimeOut**: Time in milliseconds after which the dialog is to be cancelled automatically.
- **Text**: Text to be displayed in the entry dialog.
- **Caption**: The title of the dialog.
- **Info**: Further information to be shown.
- **Default**: The default value for the input.
- **regEx**: Optional regular expression for the input.
- **Timeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **< 0**: General error, e.g. by calling outside of a test sequence
- **0**: Timeout occurred
- **1**: Dialog was closed by clicking the button **[Ok]** (successful call)
- **2**: Dialog was closed by clicking the button **[Cancel]** (form 3-6)

## Example

**Example 1**

```c
// ask for the users name and report it in the Write Window
char answer[100];
if (1 == TestWaitForStringInput("Please enter your name", 5000))
{
   TestGetStringInput(answer, 100);
   Write("name = %s", answer);
}
```

**Example 2**

```c
handle = TestWaitForStringInput("Test Text", "Test Caption", "TestString Input", "");
TestGetStringInput(resultStr, elcount(resultStr));

return = TestWaitForStringInput("Test Text", "Test Caption", "Test String Input Timeout", "", "", 5000);
TestGetStringInput(resultStr, elcount(resultStr));

return = TestWaitForStringInput("Test Text", "Test Caption", "Test String Input RegEx", "^(\\d)", "", 0);
TestGetStringInput(resultStr, elcount(resultStr));

return = TestWaitForStringInput("Test Text", "Test Caption", "Test String Input RegEx Timeout", "^(\\d)", "", 5000);
TestGetStringInput(resultStr, elcount(resultStr));
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)