[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionEncodeString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » EncodeString

# EncodeString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long EncodeString(byte output[], long& encodedSize, long maxOutputSize, char input[], dword codepage);
```

## Description

Encodes the string **input** with the encoding **codepage**.

The length of the encoded string and a terminating "\0" depend on the requested encoding. The number of bytes used in the **output** byte array is written to **encodedSize**. If the size of the output array **maxOutputSize** is not sufficient to hold the encoded string and the "\0", the functions returns an error and the content of the output array is undefined.

Characters that cannot be represented in the requested encoding, are replaced with the best matching character, selected by the Windows function `WideCharToMultiByte`.

**Example**

The CAPL string encoding usually matches the encoding of the source file. When you create a file with the **CAPL Browser**, it will save the file in an encoding which matches the language settings of your computer and write the encoding in a special comment at the beginning of the file. If the source file is encoded in UTF-16 or if an include file has a different encoding than the source file, the CAPL string encoding will be UTF-8.

## Parameters

- **output**: Target byte array.
- **encodedSize**: EncodeString writes the number of bytes used in output (including the terminating "\0") to this parameter.
- **maxOutputSize**: Size of the output array.
- **input**: The input string, using the current CAPL string encoding.
- **codepage**: Windows code page number for the encoded string. The include file **Encoding.cin** defines the following code pages:
  - CP_UTF8
  - CP_UTF16
  - CP_LATIN1
  - CP_SHIFT_JIS

## Return Values

- **0**: Success, the byte array **output** and the resulting length **encodedSize** are valid.
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
  char text[4] = "äöü";
  byte stream[10];
  long len;
  result = EncodeString(stream, len, 10, text, CP_UTF8);
  // on German Windows, len is now 7, stream is now {0xC3, 0xA4, 0xC3, 0xB6, 0xC3, 0xBC, 0};
  if (result == 0) {...}
}
```

[DecodeString](CAPLfunctionDecodeString.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)