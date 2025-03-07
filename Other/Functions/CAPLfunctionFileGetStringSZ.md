[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFileGetStringSZ.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » fileGetStringSZ

# fileGetStringSZ

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long fileGetStringSZ(char buff[], long buffsize, dword fileHandle);
```

## Method Syntax (Dynamic)

```plaintext
long File::GetStringSZ(char buff[], long buffsize);
```

## Description

The function reads a string from the specified file. Characters are read until the end of line is reached or the number of read characters is equal to **buffsize** -1. The end of line is marked either

- by a single line feed or
- a carriage return and a line feed (DOS file)

No line feed character will be contained in the buffer. See also [fileGetString.](CAPLfunctionFileGetString.md)

## Parameters

- **buff**: Buffer for the read-out string
- **buffsize**: Length of the string
- **fileHandle**: Handle to the file

## Return Values

If an error occurs, the return value is 0, else 1.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)