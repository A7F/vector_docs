[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xConvertTimeToMSSinceUTC.md)

## CAPL Functions » Car2x » C2xConvertTimeToMSSinceUTC

### C2xConvertTimeToMSSinceUTC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
Your CANoe DE product considers specific [leap seconds](../../../CANoeCANalyzer/Car2x/Hardware/c2xLeapSeconds.md) for the conversion.

### Function Syntax

```plaintext
int64 C2xConvertTimeToMSSinceUTC( int64 itsTimestamp, long refTime ); // form 1
int64 C2xConvertTimeToMSSinceUTC( long year, long month, long day, long hours, long minutes, long seconds, long milliseconds, long refTime ); // form 2
```

### Description

This function returns the elapsed milliseconds between a reference time and a time stamp.

As time stamp input either a Unix time stamp in milliseconds (form 1) or a UTC time given with year, month, hour and so on as separate parameters (form 2) can be given. Specific reference times can be set as additional parameter.

The result can be used for the time stamps defined in e.g. a CAM or a DENM.

### Parameters

- **itsTimestamp**: Unix time stamp in milliseconds (time zone UTC)
- **year**: Year of the UTC time stamp
- **month**: Month of the UTC time stamp (1..12)
- **day**: Day of the UTC time stamp (1..31)
- **hours**: Hours of the UTC time stamp since midnight (0..23)
- **minutes**: Minutes of the UTC time stamp after the hour (0..59)
- **seconds**: Seconds of the UTC time stamp after the minute (0..59)
- **milliseconds**: Milliseconds of the UTC time stamp after the second (1..999)
- **refTime**: The following reference times can be set:
  - 2004-01-01 = 0 (2004-01-01T00:00:00,000 UTC)
  - 2010-01-01 = 1 (2010-01-01T00:00:00,000 UTC)

### Return Values

- **Time stamp**: Time stamp in milliseconds
- **-1**: Error

### Example

```plaintext
int64 itsTimestamp = 0; // original time stamp
int64 itsTS2004 = 0; // converted to 2004 format
word itsTS2004mod16unsigned = 0; // -> mod16 unsigned
long itsTS2004mod32signed = 0; // -> mod32 signed
int64 itsTS2010 = 0; // converted to 2010 format
enum enumRefTime{en2004 = 0, en2010 = 1};

// get time stamp once
itsTimestamp = C2xGetITSTimestamp();

// convert time stamps into needed formats
itsTS2004 = C2xConvertTimeToMSSinceUTC(itsTimestamp, en2004);
itsTS2004mod16unsigned = C2xConvertTimeToMSSinceUTC(itsTimestamp, en2004) & 0xFFFFFFFF;
itsTS2004mod32signed = C2xConvertTimeToMSSinceUTC(itsTimestamp, en2004) & 0x7FFFFFFFFFFFFFFFLL;
itsTS2010 = C2xConvertTimeToMSSinceUTC(itsTimestamp, en2010);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
