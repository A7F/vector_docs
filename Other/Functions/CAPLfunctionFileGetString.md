# fileGetString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFileGetString.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » fileGetString

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long fileGetString (char buff[], long buffsize, dword fileHandle);
```

## Method Syntax (Dynamic)

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```plaintext
long File::GetString(char buff[], long buffsize);
```

## Description

The function reads a string from the specified file into the buffer **buff**.

Characters are read until the end of line is reached or the number of read characters is equal to **buffsize** -1. The end of line is marked either

- by a single line feed or
- a carriage return and a line feed (DOS file)

The end of line in the buffer is represented by a line feed. See also [fileGetStringSZ](CAPLfunctionFileGetStringSZ.md).

If the end of a line was encountered, the returned string contains a new line character. Else, the next call to `fileGetString` will start reading in the last line starting with the first character which didn't fit into the buffer on the previous call.

## Parameters

- **buff**: Buffer for the read-out string.
- **buffsize**: Length of the string.
- **fileHandle**: Handle to the file.

## Return Values

If an error occurs, the return value is 0, else 1.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)