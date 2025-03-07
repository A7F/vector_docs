[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetMeasurementStartTime.md)

**CAPL Functions** » **General** » **Function Overview** » **getMeasurementStartTime**

# getMeasurementStartTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long getMeasurementStartTime(long time[]);
```

## Description

Returns details about the absolute time the measurement was started.

**Note**: In CANoe DE product [offline mode](../../../CANoeCANalyzer/Windows/MeasurementSetup/MeasurementSetupWindowOfflineMode.md), the function returns the oldest start time of those stored in the logging files.

## Parameters

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

1 if successful, 0 if not (e.g., array too small).

## Example

See [addTimeToMeasurementStartTime](CAPLfunctionAddTimeToMeasurementStartTime.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)