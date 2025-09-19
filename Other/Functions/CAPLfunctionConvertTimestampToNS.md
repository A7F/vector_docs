[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionConvertTimestampToNS.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » convertTimestampToNS

# convertTimestampToNS

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
Int64 convertTimestampToNS ( dword days, dword hours, dword minutes, dword seconds );
```

## Description

Converts a time stamp given in days, hours, minutes and seconds into a nanosecond time stamp.

## Parameters

- **days**: Number of days of the time stamp.
- **hours**: Number of hours of the time stamp.
- **minutes**: Number of minutes of the time stamp.
- **seconds**: Number of seconds of the time stamp.

## Return Values

Time stamp in nanoseconds.

## Example

```plaintext
variables
{
  dword days    = 432;
  dword hours   = 125;
  dword minutes = 102;
  dword seconds = 146;
}

on start
{
  write ("1 second = %I64d ns", ConvertTimestampToNS ( 0, 0, 0, 1 ));
  write ("1 minute = %I64d ns", ConvertTimestampToNS ( 0, 0, 1, 0 ));
  write ("1 hour   = %I64d ns", ConvertTimestampToNS ( 0, 1, 0, 0 ));
  write ("1 day    = %I64d ns", ConvertTimestampToNS ( 1, 0, 0, 0 ));

  write ("Sum of %d days %d hours %d minutes %d seconds = %I64d ns", days, hours, minutes, seconds, ConvertTimestampToNS ( days, hours, minutes, seconds ));
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
