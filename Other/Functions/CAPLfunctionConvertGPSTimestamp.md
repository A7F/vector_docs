[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionConvertGPSTimestamp.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » convertGPSTimestamp

# convertGPSTimestamp

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void convertGPSTimestamp(dword timestamp, dword& year, byte& month, byte & day, byte & hour, byte & minute, byte & second);
```

## Description

Converts a GPS time stamp into UTC based date and time information.

## Parameters

- **timestamp**: The GPS time stamp (seconds since 1970-01-01 00:00).
- **year**: Receives the year of the time stamp.
- **month**: Receives the month of the time stamp (between 1 and 12).
- **day**: Receives the day of the time stamp (between 1 and 31).
- **hour**: Receives the hour of the time stamp (between 0 and 23).
- **minute**: Receives the minute of the time stamp (between 0 and 59).
- **second**: Receives the second of the time stamp (between 0 and 59).

## Return Values

—

## Example

—

[getGPSTimeString](CAPLfunctionGetGPSTimeString.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)