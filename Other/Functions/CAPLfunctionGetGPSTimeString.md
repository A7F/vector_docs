[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetGPSTimeString.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getGPSTimeString

# getGPSTimeString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void getGPSTimeString(char timeBuffer[], dword timestamp);
```

## Description

Copies a printed representation of the GPS time stamp represented as UTC date and time into the supplied character buffer. The format of the string is **ddd mmm dd hh:mm:ss jjjj** (e.g. "Fri Aug 21 15:22:24 1998").

## Parameters

- **timeBuffer**: The buffer the string will be written in. This buffer must be at least 26 characters long.
- **timestamp**: The GPS time stamp (seconds have been displayed in time stamps since 1970-01-01, 00:00). The GPS time stamp is available as system variable as soon as a GPS device is configured.

## Return Values

—

## Example

```plaintext
variables
{
  char UTC_time_and_date_buffer[30]; // needs min. 26 chars
  dword UnixTimestamp;
}

on start
{
  getGPSTimeString(UTC_time_and_date_buffer, UnixTimestamp);
}
```

[convertGPSTimestamp](CAPLfunctionConvertGPSTimestamp.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
