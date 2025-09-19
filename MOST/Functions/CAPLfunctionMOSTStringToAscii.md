[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTStringToAscii.md)

CAPL Function Overview » [MOST](../CAPLfunctionsMOSTOverview.md) » mostStringToAscii

# mostStringToAscii

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostStringToAscii(byte sourceData[], long sourceDatalen, char buffer[], long buffersize);
```

## Description

Convert MOST string to ASCII string. Unsupported characters in the input data are ignored.

**Note:**

Supported encodings:

- `0x00`: Unicode, UTF16
- `0x01`: ISO 8859/15 8 bit
- `0x02`: Unicode, UTF8
- `0x03`: RDS
- `0x04`: DAB Charset 0001
- `0x05`: DAB Charset 0010
- `0x06`: DAB Charset 0011
- `0x07`: SHIFT_JIS

## Parameters

- **sourceData**: A buffer containing the MOST string to be decoded.
- **sourceDataLen**: The size of the buffer containing the MOST string.
- **buffer**: Buffer to which the ASCII string is copied.
- **bufferSize**: Maximum number of copied ASCII string bytes (can be specified with [elcount](../../Other/Functions/CAPLfunctionElCount.md)(buffer)).

## Return Values

- **>=0**: number of converted characters
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
byte data[9] = {0x00,0x00,0x61,0x00,0x62,0x00,0x63,0x00,0x00);
char buffer[200];
if(0 < mostStringToAscii(data, elcount(data), buffer, elcount(buffer)))
    write("ASCII: %s", buffer);
```

**Output:**

```
ASCII: abc
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
