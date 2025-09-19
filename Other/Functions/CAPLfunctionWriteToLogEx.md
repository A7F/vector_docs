[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteToLogEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeToLogEx

# writeToLogEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```c
void writeToLogEx(char format[], ...);
```

## Description

Writes an output string to an ASCII or BLF logging file. Write is based on the C function `printf`.

The compiler cannot check the format string. Illegal format entries will lead to undefined results. Different to the [writeToLog](CAPLfunctionWriteToLog.md) function, neither comment characters ("//") nor time stamps will be printed at the beginning of a line.

**Note**

- The maximum length of the resulting string is limited to 1024 characters.
- Importing ASCII files with self-generated lines without comment characters into CANoe DE product can lead to problems.
- As BLF is not a human readable format, the output string cannot be seen directly in a BLF logging file, but only after a conversion into an ASCII logging file.

## Parameters

Format string, variables or [expressions](../CAPLFunctionsWriteFormatExpressions.md).

## Return Values

—

## Example

```c
// write marker with current date and time to logging file
void MarkLogFileWithTimeString(void)
{
    char timeBuffer[64];
    getLocalTimeString(timeBuffer);
    writeToLogEx("===> %s", timeBuffer);
}
```

[snprintf](CAPLfunctionSnPrintf.md) • [write](CAPLfunctionWrite.md) • [writeToLog](CAPLfunctionWriteToLog.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
