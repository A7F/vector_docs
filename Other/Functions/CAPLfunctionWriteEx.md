[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeEx

# writeEx

[Feature availability for your product](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeEx(long sink, dword severity, char format[], ...);
```

## Description

Writes the text into the last line of the specified CANoe DE product window, into a page of the Write Window or into a logging file without previously creating a new line.

To write into the CANoe DE product Trace Window please activate the CAPL **System Message** in the **predefined filters** of the [Trace Window](../../../CANoeCANalyzer/Windows/Trace/TraceWindowFilter.md).

**Note**

- When this function is executed with CANoe4SW Server Edition, the text is written into a new line of the Write Log file and not to the last line as described above.
- As BLF is not a human readable format, the output string cannot be seen directly in a BLF logging file, but only after an import into the Trace Window or a conversion into an ASCII logging file.

## Parameters

- **sink**: Sink identifier of the page to which the output will take place.

  **Values:**

  - `-4`: Output to Trace Window and logging file (only in ASC or BLF format and if the CAPL node is inserted in the Measurement Setup before the corresponding windows/blocks)
  - `-3`: Output to Trace Window (in the Measurement Setup, the CAPL node must be inserted before the Trace Window)
  - `-2`: Output to logging file (only in ASC or BLF format and if the CAPL node is inserted in the Measurement Setup before the Logging Block)
  - `-1`: Reserved
  - `0`: Output to the **System** page of the Write Window
  - `1`: Output to the **CAPL** page of the Write Window
  - `4`: Output to the **Test** page of the Write Window

- **severity**: Constant for the type of message.

  **Values:**

  - `0`: Success
  - `1`: Information
  - `2`: Warning
  - `3`: Error

- **format**: [Formatting character sequence](../CAPLFunctionsWriteFormatExpressions.md).

## Return Values

—

## Example

See [writeEx](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md) • [writeClear](CAPLfunctionWriteClear.md) • [writeCreate](CAPLfunctionWriteCreate.md) • [writeDestroy](CAPLfunctionWriteDestroy.md) • [writeLineEx](CAPLfunctionWriteLineEx.md)
