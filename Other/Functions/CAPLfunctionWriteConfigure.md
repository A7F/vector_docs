[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionWriteConfigure.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » writeConfigure

# writeConfigure

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void writeConfigure( dword sink, dword lines, dword logging, char filename[]);
```

## Description

Configures the specified page in the Write Window.

## Parameters

- **sink**: Target identifier for the page to be configured.
- **lines**: The number of lines of the page.
- **logging**: Enables the logging feature if non-zero.
- **filename**: Name of the logging file.

## Return Values

—

## Example

See [writeConfigure](CAPLfunctionsExampleWrite.md)

[write](CAPLfunctionWrite.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)