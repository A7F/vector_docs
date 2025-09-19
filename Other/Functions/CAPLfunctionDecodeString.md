[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionDecodeString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » DecodeString

# DecodeString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long DecodeString(char output[], long outputSize, byte input[], long inputSize, dword codepage);
```

## Description

Decodes the byte array **input** from the encoding **codepage** to the current CAPL string encoding.

The length of the decoded string depends on the given encoding. If the size of the output array **outputSize** is not sufficient to hold the decoded string and a terminating "\0", the functions returns an error and the content of **output** is undefined. Characters that cannot be represented in the current encoding, are replaced with the best matching character, selected by the Windows function `WideCharToMultiByte`.

**Note:**

- Unlike the `WideCharToMultiByte` Windows function, the char array output is always terminated with "\0".
- The CAPL string encoding usually matches the encoding of the source file. When you create a file with the **CAPL Browser**, it will save the file in an encoding which matches the language settings of your computer and write the encoding in a special comment at the beginning of the file. If the source file is encoded in UTF-16 or if an include file has a different encoding than the source file, the CAPL string encoding will be UTF-8.

## Parameters

- **output**: Target char array.
- **outputSize**: Size of the output array.
- **input**: The input string in encoding **codepage**, without BOM.
- **codepage**: Windows code page number for **input**. The include file **Encoding.cin** defines the following code pages:
  - CP_UTF8
  - CP_UTF16
  - CP_LATIN1
  - CP_SHIFT_JIS

## Return Values

- **0**: Success, the byte array **output** is valid.
- **-1**: Illegal character (e.g. illegal UTF8 code point).
- **-2**: Insufficient buffer space, output array is too small.
- **-3**: Internal error.

## Example

```plaintext
includes
{
  #include "Encoding.cin"
}

...
{
  int result;
  char text[10];
  byte stream[6] = {0xC3, 0xA4, 0xC3, 0xB6, 0xC3, 0xBC};
  result = DecodeString(text, 10, stream, 6, CP_UTF8);
  // on German Windows, text is now {‘ä’, ‘ö’, ‘ü’, 0}
  if (result == 0) {
    write(text);
    // Output (on a German Windows): äöü
  }
}
```

[EncodeString](CAPLfunctionEncodeString.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
