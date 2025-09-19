[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteCreate.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeCreate

# writeCreate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword writeCreate(char name[]);
```

## Description

Generates a new page in the Write Window with the specified name. The page is automatically deleted the next time a measurement starts.

## Parameters

- **name**: Name of the page to be generated.

## Return Values

Sink identifier that is valid for output to the new page.

## Example

See [writeCreate](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md) • [writeClear](CAPLfunctionWriteClear.md) • [writeDestroy](CAPLfunctionWriteDestroy.md) • [writeEx](CAPLfunctionWriteEx.md) • [writeLineEx](CAPLfunctionWriteLineEx.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
