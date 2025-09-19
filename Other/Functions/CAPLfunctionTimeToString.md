[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionTimeToString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » TimeToString

# TimeToString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TimeToString(int64 timeNS, char buffer[]);
```

## Description

Converts a timestamp or a duration (given in nanoseconds) into a string in the format `days:hours:minutes:seconds,microseconds`. Hours, minutes and seconds are always with two digits; microseconds are with six digits so they show the fraction of the second.

## Parameters

- **timeNS**: Time/duration in nanoseconds. This could be a timestamp of a frame, the time given by [timeNowInt64](CAPLfunctionTimeNowNS.md), or a time measured with the [CAPLProfiler class](../../ObjectOrientedProg/CAPLfunctionsOOPCAPLProfiler.md).

- **buffer**: Receives the string. Must be at least 18 characters long (more if the duration is >= 10 days).

## Return Values

- **0**: Success
- **-1**: Error, e.g. buffer too small.

## Example

```plaintext
on sysvar MySysVar
{
  char timeString[20];
  TimeToString(timeNowInt64(), timeString);
  Write("MySysVar was changed at simulation time %s", timeString);
}
```

[convertTimestamp](CAPLfunctionConvertTimestamp.md) • [getLocalTimeString](CAPLfunctionGetLocalTimeString.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
