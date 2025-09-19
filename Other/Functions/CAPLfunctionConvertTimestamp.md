[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionConvertTimestamp.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » convertTimestamp, convertTimestampNS

# convertTimestamp, convertTimestampNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void convertTimestamp(dword timestamp, dword& days, byte& hours, byte& minutes, byte& seconds, word& milliSeconds, word& microSeconds); // form 1`
- `void convertTimestampNS(qword timestamp, dword& days, byte& hours, byte& minutes, byte& seconds, word& milliSeconds, word& microSeconds, word& nanoSeconds); // form 2`

## Description

Converts a time stamp to separate parts.

(form 1: maximum time: .2^32 * 10 microseconds = 11 hours, 55 minutes, 49 seconds, 672 milliseconds, 96 microseconds).

## Parameters

- **timestamp**:
  - time stamp in 10 microseconds (form 1)
  - time stamp in nanoseconds (form 2)
- **days**: Receives the days of the time stamp
- **hours**: Receives the hours the time stamp (between 0 and 23)
- **minutes**: Receives the minutes of the time stamp (between 0 and 59)
- **seconds**: Receives the seconds of the time stamp (between 0 and 59)
- **milliseconds**: Receives the milliseconds of the time stamp (between 0 and 999)
- **microseconds**: Receives the microseconds of the time stamp (between 0 and 999)
- **nanoseconds** (only form 2): Receives the nanoseconds of the time stamp (between 0 and 999)

## Return Values

—

## Example

```plaintext
on envVar EnvGearUp
{
   dword d;
   byte h, m, s;
   word ms, us, ns;
   convertTimestampNS(timeNowNS(), d, h, m, s, ms, us, ns);
   write("Gear up at %d days, %d::%d::%d,%d.%d.%d", d, h, m, s, ms, us, ns);
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
