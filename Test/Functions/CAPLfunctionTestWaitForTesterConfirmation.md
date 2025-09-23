# TestWaitForTesterConfirmation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForTesterConfirmation(char text[]);`
- `long TestWaitForTesterConfirmation(char[] text, unsigned long timeout);`
- `long TestWaitForTesterConfirmation(char[] text, unsigned long timeout, char[] heading, char[] resource, char[] resourceCaption);`

## Description

Creates a popup window that presents the given string to the tester. The tester can acknowledge the window with **Yes** or **No**.

The window contains a field for entering a comment that is automatically adopted into the test report.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

Even when this function is called by different test modules, only one of these popup windows is active at a time.

- The 1st wait function has no timeout so it waits for the confirmation of the tester.
- The 2nd wait function has a timeout, i.e., the dialog is automatically terminated after the timeout expires.
- The 3rd wait function has a timeout and can show a resource, i.e., the dialog can show additional information.

## Parameters

- **text**: This is shown in the popup window. The maximum length of the string is limited (4096 characters).
- **timeout**: Time in milliseconds after which the dialog is automatically ended. Transmission of 0: no timeout controlling.
- **heading**: A heading above the dialog text. The maximum length of the string is limited (256 characters).
- **resource**: A URL or file path. The maximum length of the string is limited (512 characters). Pictures are shown in the dialog itself, for other resources a link is shown. Supported picture types are: **bmp**, **jpg**, **png**, **gif**. For arbitrary files, the application registered for that file type on the computer is used to open it when the user clicks the link. Relative file paths are based on the configuration or test setup which contains the test module.
- **resourceCaption**: A caption respectively a description for the resource. The maximum length of the string is limited (256 characters).

## Return Values

- **0**: Timeout occurred.
- **1**: The tester clicked **Yes**.
- **2**: The tester clicked **No**.
- **-1**: General error, e.g., due to a call outside of a test sequence.
- **-2**: Constraint occurred.

## Example

```c
// waits for the answer of the user
long result;
result = TestWaitForTesterConfirmation("Any text or question", 10000);
```
