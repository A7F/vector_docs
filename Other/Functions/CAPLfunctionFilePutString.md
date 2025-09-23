[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionFilePutString.md)

**CAPL Functions** » **General** » **Function Overview** » **filePutString**

# filePutString

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long filePutString (char buff[], long buffsize, dword fileHandle);
```

## Method Syntax (Dynamic)

```plaintext
long File::PutString(char buff[], long buffsize);
```

## Description

This function writes a string in the specified file.

## Parameters

- **buff**: Buffer for the read-in string
- **buffsize**: Number of characters
- **fileHandle**: Handle to the file

## Return Values

If an error occurs, the return value is 0, else 1.

## Example

See [File Functions](CAPLfunctionsExapmleFileFunctions.md)

[Class: File](../../ObjectOrientedProg/CAPLfunctionsOOPFile.md)
