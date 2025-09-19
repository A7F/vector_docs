[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionAddTimeToMeasurementStartTime.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » addTimeToMeasurementStartTime

# addTimeToMeasurementStartTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long addTimeMeasurementStartTime(int64 timeSpan, long time[]);
```

## Description

Calculates the absolute date/time of the measurement start plus an offset (e.g. a timestamp).

**Note**: In [offline mode](../../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindowOfflineMode.md), the function returns the oldest start time of those stored in the logging files.

## Parameters

- **timeSpan**: Time to be added to the measurement start time, e.g. a timestamp of a measured frame.
- **time**: An array of type long with at least 8 entries. The entries of the array will be filled with the following information:
  - **0**: Milliseconds (0 - 999)
  - **1**: Seconds (0 - 59)
  - **2**: Minutes (0 - 59)
  - **3**: Hours (0 - 23)
  - **4**: Day of month (1 - 31)
  - **5**: Month (0 - 11)
  - **6**: Year (0 - xxx, offset of 1900, e.g. 117 = 2017)
  - **7**: Day of week (0 - 6, Sunday is 0)

## Return Values

1 if successful, 0 if not (e.g. array too small).

## Example

```plaintext
on errorframe
{
  long time[8];
  addTimeToMeasurementStartTime(timeNowNS(), time);
  write("ErrorFrame occured on %02d/%02d/%02d %02d:%02d:%02d.%-3d",
  time[5]+1, time[4], time[6]-100, time[3], time[2], time[1], time[0]);
  getMeasurementStartTime(time);
  write("Measurement was started on %02d/%02d/%02d %02d:%02d:%02d.%-3d",
  time[5]+1, time[4], time[6]-100, time[3], time[2], time[1], time[0]);
}

// Output e.g.:
// ErrorFrame occured on 08/15/17 14:39:46.787
// Measurement was started on 08/15/17 14:39:29.547
```

[getMeasurementStartTime](CAPLfunctionGetMeasurementStartTime.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
