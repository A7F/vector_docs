[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionConvertString.md)

**CAPL Functions** » **General** » **Function Overview** » **ConvertString**

# ConvertString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long ConvertString(byte output[], long& encodedSize, long maxOutputSize, dword outputCodepage, byte input[], long inputSize, dword inputCodepage);
```

## Description

Converts a string from one encoding to another encoding. The length of the converted string depends on the requested encoding. The number of bytes used in the output byte array is written to **encodedSize**. If the size of the output array **maxOutputSize** is not sufficient to hold the converted string and a terminating "\0", the function returns an error and the content of output is undefined. Characters that cannot be represented in the requested encoding are replaced with the best matching character, selected by the Windows function `WideCharToMultiByte`.

## Parameters

- **output**: Target byte array.
- **encodedSize**: ConvertString writes the number of bytes used in output (including the terminating "\0") to this parameter.
- **maxOutputSize**: Size of the output array.
- **outputCodepage**: Windows code page number for output. The include file Encoding.cin defines the following code pages:
  - CP_UTF8
  - CP_UTF16
  - CP_LATIN1
  - CP_SHIFT_JIS
- **input**: The input string in encoding **codepage**, without BOM.
- **inputSize**: Length of the input string in bytes.
- **inputCodepage**: Windows code page number for **input**. The include file **Encoding.cin** defines the following code pages:
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
// Convert a system variable string value (e.g. input from a panel) into UTF-16 and vice versa
includes
{
  #include "Encoding.cin"
}

// handle input of a string, e.g. from a panel
on sysvar TestVars::StringSV
{
  byte data[100]; long nrOfBytes; byte data2[200]; long res;
  // get the string in UTF-8
  sysGetVariableData(sysvar::TestVars::StringSV, data, nrOfBytes);
  // convert it to UTF-16
  res = ConvertString(data2, nrOfBytes, elcount(data2), CP_UTF16, data, nrOfBytes, CP_UTF8);
  // now use the UTF-16 bytes, e.g. send them over a network
  // here simulated by using a system variable of type data
  sysSetVariableData(sysvar::TestVars::DataVar, data2, nrOfBytes);
}

// receive UTF-16 data, e.g. from a network
// here simulated by using a system variable of type data
on sysvar TestVars::DataVar
{
  byte data[200]; long nrOfBytes; byte data2[100]; long res;
  sysGetVariableData(sysvar::TestVars::DataVar, data, nrOfBytes);
  // data is the string in UTF-16; convert it to UTF-8
  res = ConvertString(data2, nrOfBytes, elcount(bytes), CP_UTF8, data, nrOfBytes, CP_UTF16);
  // copy the string into a system variable of type string, e.g. to display it in a panel
  sysSetVariableData(sysvar::TestVars::OutStringVar, data2, nrOfBytes);
}
```

[DecodeString](CAPLfunctionDecodeString.md) • [EncodeString](CAPLfunctionEncodeString.md) • [String Literal](../CAPLfunctionsStringLiteral.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
