[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForByteInput.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForByteInput

# TestWaitForByteInput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestWaitForByteInput(char text[], char caption[], char info[]); // form 1
long TestWaitForByteInput(char text[], char caption[], char info[], dword timeout); // form 2
```

## Description

This function opens a dialog for byte array input. Optionally you can set some timeout in ms. Afterwards the dialog will be closed. You can optionally define some default input for the dialog.

## Parameters

- **Text**: Text to be displayed in the entry dialog.
- **Caption**: The title of the dialog.
- **Info**: Further information to be shown
- **Timeout**: Optional timeout for the dialog in ms. Transmission of 0: no timeout controlling.

## Return Values

- **1**: Dialog was closed by clicking the button **[Ok]** (successful call)
- **2**: Dialog was closed by clicking the button **[Cancel]**

## Example

```plaintext
return = TestWaitForByteInput("Test Text", "Test Caption", "Test Byte Input", 0);
TestGetByteInput(resultByte, elcount(resultByte));

return = TestWaitForByteInput("Test Text", "Test Caption", "Test Byte Input Timeout", 5000);
TestGetByteInput(resultByte, elcount(resultByte));
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
