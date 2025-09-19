[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFileWriteBinaryBlock.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » fileWriteBinaryBlock

# fileWriteBinaryBlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long fileWriteBinaryBlock (byte buff[], long buffsize, dword fileHandle);
```

## Method Syntax (Dynamic)

```plaintext
long File::WriteBinaryBlock(byte buff[], long buffsize);
```

## Description

This function writes **buffsize** bytes in the specified file.

## Parameters

- **buff**: Buffer, with the binary data to be written.
- **buffersize**: Number of bytes to be written.
- **fileHandle**: Handle to the file.

## Return Values

The function returns the number of bytes written.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
