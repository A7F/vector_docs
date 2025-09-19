[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFileGetBinaryBlock.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » fileGetBinaryBlock

# fileGetBinaryBlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long fileGetBinaryBlock (byte buff[], long buffsize, dword fileHandle);
```

## Method Syntax (Dynamic)

```plaintext
long File::GetBinaryBlock(byte buff[], long buffsize);
```

## Description

The function reads characters from the specified file in binary format. The source file must be opened in binary format.

## Parameters

- **buff**: Buffer
- **buffsize**: Maximum of buffsize characters
- **fileHandle**: Handle to the file

## Return Values

The function returns the number of characters read.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
