[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLFunctionC2xConvertMod32TsToUTC.md)

## C2xConvertMod32TsToUTC

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xConvertMod32TsToUTC

### Valid for: CANoe DE

---

**Note**  
Your CANoe DE product considers specific leap seconds for the conversion.

### Function Syntax

```plaintext
long C2xConvertMod32TsToUTC( int64 mod32Ts, long refTime, long buffersize, long time[] )
```

### Description

This function converts a mod32 time stamp in milliseconds since a reference time into a UTC time stamp as an array of type long with separate values for year, month, day, and so on.

### Parameters

- **mod32Ts**: Time stamp in milliseconds since the reference time.
- **refTime**: The following reference times can be set:
  - 0: 2004-01-01 (2004-01-01T00:00:00,000 UTC)
  - 1: 2010-01-01 (2010-01-01T00:00:00,000 UTC).
- **buffersize**: Size of the buffer to be filled with the UTC time stamp.
- **time**: Array of long which contains the UTC time in the following format:
  - 0: milliseconds (0..999)
  - 1: seconds (0..60)
  - 2: minutes (0..60)
  - 3: hours (0..24)
  - 4: day of month (1..31)
  - 5: month (0..11)
  - 6: year (starting with 1900)
  - 7: day of week (0..7)
  - 8: day of year (0..365)

### Return Values

- **0**: Success
- **-1**: Error

### Example

```plaintext
enum enumRefTime{en2004 = 0, en2010 = 1};
long utcTime[9];

// milliseconds from 01.01.2004 00:00:00 UTC to 01.04.2019 00:00:00 UTC
int64 msSince2004 = 481161600000LL;

if (C2xConvertMod32TsToUTC(msSince2004, en2004, elCount(utcTime), utcTime) == 0)
{
  // output (leap seconds are considered): Date 2019-03-31 Time 23:59:55.000 UTC
  write("Date %d-%02d-%02d Time %02d:%02d:%02d.%03d UTC", 1900+utcTime[6], utcTime[5]+1, utcTime[4], utcTime[3], utcTime[2], utcTime[1], utcTime[0]);
}
```

---

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
