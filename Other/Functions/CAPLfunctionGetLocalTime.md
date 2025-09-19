[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetLocalTime.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getLocalTime

# getLocalTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void getLocalTime(long time[]);
```

## Description

Returns details to the current date and time in an array of type long.

**Note for use in distributed mode**

- This function always returns the local time of the user computer.

## Parameters

An array of type long with at least 9 entries.

The entries of the array will be filled with the following information:

- **0**: Seconds (0 - 59)
- **1**: Minutes (0 - 59)
- **2**: Hours (0 - 23)
- **3**: Day of month (1 - 31)
- **4**: Month (0 - 11)
- **5**: Year (0 - xxx, offset of 1900, e.g. 117 = 2017)
- **6**: Day of week (0 - 6, Sunday is 0)
- **7**: Day of Year (0 - 365)
- **8**: Flag for daylight saving time (0 - 1, 1 = daylight saving time)

## Return Values

—

## Example

```plaintext
...
long tm[9];
getLocalTime(tm);
// now tm contains the following entries:
// tm[0] = 3; (seconds)
// tm[1] = 51; (minutes)
// tm[2] = 16; (hours)
// tm[3] = 21; (day of month)
// tm[4] = 7; (month starting with 0)
// tm[5] = 98; (year)
// tm[6] = 5; (weekday)
// tm[7] = 232; (day of year)
// tm[8] = 1; (Summer time)
...
```

[getLocalTimeString](CAPLfunctionGetLocalTimeString.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
