[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionBytesToString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » BytesToString

# BytesToString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long BytesToString(byte input[], char format[], char sep[], char output[]); // form 1
long BytesToString(byte input[], char format[], char sep[], char output[], dword outputStartIndex); // form 2
```

## Description

Converts a byte array to a formatted string. For each byte in the input, the format is applied and the result is written to the output. Between the written bytes, the separator string is inserted. It is not inserted before the first byte or after the last byte.

## Parameters

- **input**: The byte array to be written to the output.
- **format**: The format in which to write the bytes to the output. It can be an arbitrary `printf` format string so long as only a single parameter is written (i.e. only a single % is present in the string).
- **sep**: A separator string that is written in between the formatted bytes.
- **output**: The string in which the formatted input is written. If it is not sufficiently long to hold the output, the string will be empty and the intrinsic will return -1.
- **outputStartIndex**: The index in the output at which the start writing the formatted byte array. Any characters before that index are left unchanged.

## Return Values

- **>=0**: Indicates a successful function execution and is the number of characters written into the output (without the trailing null byte).
- **-1**: The output was not large enough to hold the result.
- **-2**: The format string was malformed.

## Example

```plaintext
byte input[5] = {8, 9, 10, 11, 12};
char output[20];
long res;
res = BytesToString(input, "%02X", "-", output);
Write("Result: %d, Output: %s", res, output);
```

[StringToBytes](CAPLfunctionStringToBytes.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
