[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteToLog.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeToLog

# writeToLog

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeToLog(char format[], ...);
```

## Description

Writes an output string to an ASCII or BLF logging file. Write is based on the C function `printf`.

The compiler cannot check the format string. Illegal format entries will lead to undefined results. Different to the [writeToLogEx](CAPLfunctionWriteToLogEx.md) function, comment characters ("//") and a time stamp at the beginning of each line will be printed.

**Note**

- The maximum length of the resulting string is limited to 1024 characters.
- As BLF is not a human readable format, the output string cannot be seen directly in a BLF logging file, but only after a conversion into an ASCII logging file.

## Parameters

Format string, variables or [expressions](../CAPLFunctionsWriteFormatExpressions.md).

## Return Values

—

## Example

```c
void MarkLogFile(int marker) {
// marks line of ASCII logging file with an integer
writeToLog("===> %d",marker);
}
```

[snprintf](CAPLfunctionSnPrintf.md) • [write](CAPLfunctionWrite.md) • [writeToLogEx](CAPLfunctionWriteToLogEx.md)
