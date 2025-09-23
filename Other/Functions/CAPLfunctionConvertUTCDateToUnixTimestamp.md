[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionConvertUTCDateToUnixTimestamp.md)

**CAPL Functions** » **General** » **Function Overview** » **convertUTCDateToUnixTimestamp**

# convertUTCDateToUnixTimestamp

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
Int64 convertUTCDateToUnixTimestamp(dword year, byte month, byte day, byte hour, byte minute, byte second);
```

## Description

Converts the given UTC time and date into a UNIX timestamp (seconds since 1970-01-01).

## Parameters

- **year**: The year.
- **month**: The month (between 1 and 12).
- **day**: The day (between 1 and 31).
- **hour**: The hour (between 0 and 23).
- **minute**: The minute (between 0 and 59).
- **second**: The second (between 0 and 60, since leap seconds are supported).

## Return Values

- UNIX timestamp (seconds since 1970-01-01) corresponding to the input parameters.
- -1 if input parameters are invalid.

## Example

```plaintext
stack Int64 unixTimestamp;
unixTimestamp = convertUTCDateToUnixTimestamp(2033, 05, 18, 03, 33, 20);
write("The unix timestamp will be %I64d", unixTimestamp);
```

[convertTimestamp, convertTimestampNS](CAPLfunctionConvertTimestamp.md) • [getGPSTimeString](CAPLfunctionGetGPSTimeString.md)
