[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetByteInput.md)

## TestGetByteInput

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetByteInput

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

### Function Syntax

`TestGetByteInput(byte[] result, dword resultSize);`

### Description

After a dialog with byte input is closed you can use this function to get the input.

### Parameters

- **result**: Some byte array you can save the input

### Return Values

- **resultSize**: Size of the byte array

### Example

```plaintext
handle = TestWaitForByteInput("Test Text", "Test Caption", "Test Byte Input", 0);
TestGetByteInput(resultByte, elcount(resultByte));
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)