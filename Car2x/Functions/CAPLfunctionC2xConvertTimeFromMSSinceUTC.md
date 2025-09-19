# C2xConvertTimeFromMSSinceUTC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
Your CANoe DE product considers specific [leap seconds](../../../CANoeCANalyzer/Car2x/Hardware/c2xLeapSeconds.md) for the conversion.

## Function Syntax

```plaintext
long C2xConvertTimeFromMSSinceUTC( int64 milliseconds, long refTime, long buffersize, char buffer[] ); // form 1
long C2xConvertTimeFromMSSinceUTC( int64 milliseconds, long refTime, long buffersize, long time[] ); // form 2
```

## Description

This function converts a time stamp in milliseconds since a reference time into a UTC time stamp in string format (form 1) or as long array with separate values for year, month, day and so on (form 2).

## Parameters

- **milliseconds**: Time stamp in milliseconds since reference time.
- **refTime**: The following reference times can be set:
  - 0: 2004-01-01 (2004-01-01T00:00:00,000 UTC)
  - 1: 2010-01-01 (2010-01-01T00:00:00,000 UTC)
- **buffersize**: Size of the buffer to be filled with the UTC time stamp in string format: "YYYY-MM-DDThh:mm:ss,ddd UTC".
- **buffer**: Buffer to be filled with the UTC time stamp in string format.
- **time**: Array of long which contains the UTC time stamp in the following format:
  - 0: milliseconds (0..999)
  - 1: seconds (0..60)
  - 2: minutes (0..60)
  - 3: hours (0..24)
  - 4: day of month (1..31)
  - 5: month (0..11)
  - 6: year (starting with 1900)
  - 7: day of week (0..7)
  - 8: day of year (0..365)

## Return Values

- **0**: Success
- **-1**: Error

## Example

```plaintext
int64 itsTS2004 = 300000000000LL; // original time stamp in 2004 format
enum enumRefTime{en2004 = 0, en2010 = 1};
char buffer[40];
long utcTime[9];

if (C2xConvertTimeFromMSSinceUTC(itsTS2004, en2004, elcount(buffer), buffer) == 0)
{
  // output: Time stamp 2013-07-04T05:19:57.000 UTC
  write("Time stamp %s", buffer);
}

if (C2xConvertTimeFromMSSinceUTC(itsTS2004, en2004, elcount(utcTime), utcTime) == 0)
{
  write("Time stamp %d-%02d-%02dT%02d:%02d:%02d.%03d UTC", 1900+utcTime[6], utcTime[5]+1, utcTime[4], utcTime[3], utcTime[2], utcTime[1], utcTime[0]);
}
```
