# StringToBytes

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long StringToBytes(char input[], char format[], char sep[], byte output[]); // form 1
long StringToBytes(char input[], dword inputStartIndex, char format[], char sep[], byte output[]); // form 2
```

## Description

Parses a byte array from a formatted string. It is the opposite of the intrinsic [BytesToString](CAPLfunctionBytesToString.md) and can parse the output of that function. The input string must contain a series of numbers formatted with the format specifier and optional separators in between. Given that the output is read into a byte array, no number can be larger than 255.

## Parameters

- **input**: The input string from which to parse the byte array. It must be formatted according to the arguments format and sep in order for the parsing to succeed.
- **inputStartIndex**: The index at which to start parsing the input. All characters before the start index are ignored.
- **format**: The `printf` format specifier with which the input is formatted. It must contain the formatting for a single number, i.e. exactly one `%` must be present in the format.
- **sep**: The separator that separates individual formatted numbers in the input. So long as the format specifies the number of characters per byte being parsed, this string can also be empty.
- **output**: The output into which the parsed bytes are written. It must be large enough to hold all bytes from the input, otherwise the intrinsic will return -1.

## Return Values

- **>=0**: Indicates a successful function execution and is the number of bytes parsed and written into the output.
- **-1**: The output was not large enough to hold the result.
- **-2**: The input does not match the format string and separator, a number in the input did not fit into a byte, or the format string was malformed.

## Example

```plaintext
byte output[5];
long res;
res = StringToBytes("05-0F-FF", "%02X", "-", output);
Write("Result: %d, Output: %d %d %d", res, output[0], output[1], output[2]);
```

[BytesToString](CAPLfunctionBytesToString.md)
