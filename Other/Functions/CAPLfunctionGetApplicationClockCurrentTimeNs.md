[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetApplicationClockCurrentTimeNs.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getApplicationClockCurrentTimeNs

# getApplicationClockCurrentTimeNs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
byte getApplicationClockCurrentTimeNs(int64& domainTimeNs, long& timescale, int64& leapSeconds);
```

## Description

Supplies the current / absolute domain-time of the Application-Clock. Additionally, the function provides information about the used timescale and the number of leap seconds. The Application-Clock can be configured using the Vector Hardware Manager.

## Parameters

- **domainTimeNs**: Absolute time since epoch in nanoseconds. Does not contain any leap seconds.
- **timescale**: The timescale of the domain. Valid values are:
  - **2 (PTP):**
    - Epoch: 1970 TAI.
    - The unit of measure of time is the SI second (International System of Units) as realized on the rotating geoid. One nanosecond is equal to one billionth of an SI-second (1 nanosecond = 1/1,000,000,000 of a second).
  - **3 (PERFORMANCE_COUNTER):**
    - Epoch: arbitrary.
    - The timescale is not traceable to international standards.
  - **4 (ARBITRARY):**
    - Epoch: arbitrary.
    - The timescale is not traceable to international standards.
  - **5 (RTC)**
    - Epoch: 1970 TAI.
    - The timescale is not traceable to international standards.
- **leapSeconds**: Number of leap seconds.

## Return Values

- **0**: FAILURE: Failed to get the current domain-time.
- **1**: SUCCESS: The current domain time was successfully retrieved.

## Example

```plaintext
int64 GetDomainTimeNs()
{
  int64 domainTimeNs;
  long timescale;
  int64 leapSeconds;

  if (getApplicationClockCurrentTimeNs(domainTimeNs, timescale, leapSeconds) == 0)
  {
    write("failed to get current domain-time");
    return 0;
  }
  return domainTimeNs;
}
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
