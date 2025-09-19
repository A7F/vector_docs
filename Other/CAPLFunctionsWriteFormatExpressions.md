[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/CAPLFunctionsWriteFormatExpressions.md)

[CAPL Functions](../CAPLfunctions.md) » [General](CAPLGeneralStartPage.md) » Write Format Expressions

# Write Format Expressions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE • CANoe:lite DE • CANoe4SW:lite DE

Formatting takes place via placeholders within the format string. For example, if a program wanted to print out the current simulation time to the [Write Window](../../CANoeCANalyzer/Windows/Write/WriteWindow.md), it could present the output by prefixing it with `The current simulation time is`, and using the format specifier `%lld` to denote that it wants the number of nanoseconds for the simulation time to be shown immediately after that message, it may use the format string:

`Write("The current simulation time is %lld ns", timeNowInt64());`

## Comparison to C / C++

The placeholder format is very similar to the one used in the C or C++ languages. In almost all cases, you can use the format known to you if you have experience in one of those languages. Some differences include:

- The flag for thousands separators ("'") is not supported.
- The types "a" and "A" are not supported.
- The type "n" is not supported.
- The exponent with types "e" and "E" always contains three digits on windows.

## Syntax

The syntax for a format placeholder is

`%[flags][width][.precision][length]type`

If a `%` sign shall be printed, it must be masked by another `%` sign: `"%%"`.

## Flags Field

The Flags field can be zero or more (in any order) of:

- **- (minus)**: Left-align the output of this placeholder. (The default is to right-align the output.)
- **+ (plus)**: Prepends a plus for positive signed-numeric types. positive = +, negative = -. The default does not prepend anything in front of positive numbers.
- **(space)**: Prepends a space for positive signed-numeric types. positive = , negative = -. This flag is ignored if the + flag exists. The default does not prepend anything in front of positive numbers.
- **0 (zero)**: When the 'width' option is specified, prepends zeros for numeric types. The default prepends spaces. For example, `Write("%4X",3)` produces ` 3`, while `Write("%04X",3)` produces `0003`.
- **# (hash)**: Alternate form:
  - For `g` and `G` types, trailing zeros are not removed.
  - For `f`, `F`, `e`, `E`, `g`, `G` types, the output always contains a decimal point.
  - For `o`, `x`, `X` types, the text `0`, `0x`, `0X`, respectively, is prepended to non-zero numbers.

## Width Field

The width field specifies a **minimum** number of characters to output and is typically used to pad fixed-width fields in tabulated output, where the fields would otherwise be smaller, although it does not cause truncation of oversized fields.

The width field may be omitted, or a numeric integer value, or a dynamic value when passed as another argument when indicated by an asterisk `*`. For example, `Write("%*d", 5, 10)` will result in ` 10` being printed, with a total width of 5 characters.

Though not part of the width field, a leading zero is interpreted as the zero-padding flag mentioned above, and a negative value is treated as the positive value in conjunction with the left-alignment `-` flag also mentioned above.

## Precision Field

The precision field usually specifies a **maximum** limit on the output, depending on the particular formatting type. For the e, E and f types, it specifies the number of digits to the right of the decimal point that the output should be rounded. For the g and G type, it specifies the number of all digits before and after the decimal point combined (but without the decimal point itself). For all floating point types, the default precision is 6 digits.

For the string type, it limits the number of characters that should be output, after which the string is truncated.

The precision field may be omitted, or a numeric integer value, or a dynamic value when passed as another argument when indicated by an asterisk *. For example, `Write("%.*s", 3, "abcdef")` will result in `abc` being printed.

## Length Field

The length field is needed for some of the integer types to tell the program how large the data type is. It is also sometimes different depending on whether the program runs on Windows or on Linux.

- **int**: 2 Bytes
- **long**: 4 Bytes, Length Field Windows: l
- **int64**: 8 Bytes, Length Field Windows: I64 or ll, Length Field Linux: l or ll
- **byte**: 1 Byte
- **word**: 2 Bytes
- **dword**: 4 Bytes, Length Field Windows: l
- **qword**: 8 Bytes, Length Field Windows: I64 or ll, Length Field Linux: l or ll

## Type Field

The type field depends on the data type of the expression that shall be printed, and can also designate different ways that the value is printed.

- **int, long, int64**: signed integer, decimal display, Type: d
- **byte, word, dword, qword**: unsigned integer, decimal display, Type: u
- **byte, word, long, dword, int64, qword**: integer, hexadecimal display. Upper-case X in the type field means upper-case in the output, Type: x or X
- **byte, word, long, dword, int64, qword**: integer, octal display, Type: o
- **float, double**: floating point, fixed point notation, e.g., 3.141593, Type: f
- **float, double**: floating point, exponential notation, e.g., 3.141593e+000. The exponent will have 3 digits on Windows; it will have 2 or 3 digits on Linux. Upper-case E in the type field means an upper-case E in the output, Type: e or E
- **float, double**: floating point, use either fixed point or exponential notation, whichever is shorter, Type: g or G
- **char**: character, Type: c
- **char[]**: string, Type: s

**Note**: The `%n` format is invalid and must not be used.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
