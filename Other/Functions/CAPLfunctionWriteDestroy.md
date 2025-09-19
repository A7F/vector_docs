[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteDestroy.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeDestroy

# writeDestroy

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeDestroy(dword sink);
```

## Description

Removes the specified page from the Write Window. Only pages that have been created with the aid of the [writeCreate](CAPLfunctionWriteCreate.md) function can be removed.

## Parameters

- **sink**: Target identifier for the page to be removed.

## Return Values

—

## Example

See [writeDestroy](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md) • [writeClear](CAPLfunctionWriteClear.md) • [writeCreate](CAPLfunctionWriteCreate.md) • [writeEx](CAPLfunctionWriteEx.md) • [writeLineEx](CAPLfunctionWriteLineEx.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
