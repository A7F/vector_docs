[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteLineEx.md)

**CAPL Functions** » **General** » **Function Overview** » **writeLineEX**

# writeLineEX

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeLineEx(long sink, dword severity, char format[], ...);
```

## Description

Writes the text into a new line of the specified CANoe DE product window, into a page of the CANoe DE product Write Window or into a logging file.

To write into the CANoe DE product Trace Window please activate the CAPL **System Message** in the **predefined filters** of the [Trace Window](../../../CANoeCANalyzer/Windows/Trace/TraceWindowFilter.md).

**Note**: As BLF is not a human readable format, the output string cannot be seen directly in a BLF logging file, but only after an import into the Trace Window or a conversion into an ASCII logging file.

## Parameters

- **sink**: The target identifier of the page to which the output will take place.

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

  For output to a logging file, this parameter specifies whether comments should be output (severity == 0). If this is not desired, set severity = 1.

- **format**: [Formatting character sequence](../CAPLFunctionsWriteFormatExpressions.md).

## Return Values

—

## Example

See [writeLineEx](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md) • [writeClear](CAPLfunctionWriteClear.md) • [writeCreate](CAPLfunctionWriteCreate.md) • [writeDestroy](CAPLfunctionWriteDestroy.md) • [writeEx](CAPLfunctionWriteEx.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)