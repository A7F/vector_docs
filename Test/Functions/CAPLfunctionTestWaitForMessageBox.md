[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMessageBox.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForMessageBox**

# TestWaitForMessageBox

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `TestWaitForMessageBox(char[] text, unsigned long timeout, char[] heading, char[] resource, char[] resourceCaption, unsigned long buttons, int showCommentTextbox);`
- `TestWaitForMessageBox(char[] text, unsigned long timeout, char[] heading, unsigned long buttons);`
- `TestWaitForMessageBox(char[] text, unsigned long timeout);`

## Description

Creates a popup window that presents the given string to the tester. The tester can acknowledge the window with the selected button collection. Optionally, the window contains a field for entering a comment that is automatically adopted into the test report.

The function is not allowed in [standalone mode](../../../CANoeCANalyzer/RTSetup/StandaloneMode/StandaloneModeConcept.md). Errors are reported as **error in test system** or **fail** in case of 2-valued verdict concept.

Even when this function is called by different test modules, only one of these popup windows can be active at a time.

## Parameters

- **text**: This is shown in the popup window. The maximum length of the string is limited (4096 characters).
- **timeout**: Time in milliseconds after which the dialog is automatically ended. Transmission of 0: no timeout controlling.
- **heading**: A heading above the dialog text. The maximum length of the string is limited (256 characters).
- **resource**: A URL or file path. The maximum length of the string is limited (512 characters). Pictures are shown in the dialog itself, for other resources a link is shown. Supported picture types are: **bmp**, **jpg**, **png**, **gif**. For arbitrary files, the application registered for that file type on the computer is used to open it when the user clicks the link. Relative file paths are based on the configuration or test setup which contains the test module.
- **resourceCaption**: A caption or description for the resource. The maximum length of the string is limited (256 characters).
- **buttons**: Selector for visible button collection
  - **0**: OK
  - **1**: OK and Cancel
  - **2**: Abort, Retry and Unclear
  - **3**: Yes, No and Cancel
  - **4**: Yes and No
  - **5**: Retry and Cancel
- **showCommentTextbox**: Select whether the comment Textbox is visible or not.

## Return Values

- **0**: Timeout occurred.
- **1**: The tester clicked **OK**.
- **2**: The tester clicked **Cancel**.
- **3**: The tester clicked **Abort**.
- **4**: The tester clicked **Retry**.
- **5**: The tester clicked **Unclear**.
- **6**: The tester clicked **Yes**.
- **7**: The tester clicked **No**.
- **-1**: General error, e.g., due to a call outside of a test sequence.

## Example

```c
// waits for the answer of the user
long result;
result = TestWaitForMessageBox("Any text or question", 10000);
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
