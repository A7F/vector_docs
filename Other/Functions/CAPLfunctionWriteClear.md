[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteClear.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeClear

# writeClear

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeClear(dword sink);
```

## Description

Clears the contents of the specified page in the Write Window.  
You can use the following constants for the target identifier or type of message:

```plaintext
// write sinks
dword WRITE_SYSTEM = 0;
dword WRITE_CAPL = 1;
```

In addition, you can use one of the target identifiers returned by the function [writeCreate](CAPLfunctionWriteCreate.md). You can clear all tabs using "**-1**" as parameter. The **Overview** page can’t be cleared solely.

## Parameters

- **sink**: Target identifier for the page to be deleted.

## Return Values

—

## Example

See [writeClear](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md) • [writeCreate](CAPLfunctionWriteCreate.md) • [writeDestroy](CAPLfunctionWriteDestroy.md) • [writeEx](CAPLfunctionWriteEx.md) • [writeLineEx](CAPLfunctionWriteLineEx.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
