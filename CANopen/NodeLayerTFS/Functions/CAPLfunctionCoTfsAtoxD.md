[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsAtoxD.md)

**CAPL Functions** » [CANopen](../../CAPLfunctionsCANopenOverview.md) » [Test Feature Set Node Layer](../CAPLfunctionsCANopenNLTFSLevelOverview.md) » coTfsatoxD

# coTfsatoxD

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
This function should not be used in user specific CAPL programs.

## Function Syntax

```
dword coTfsatoxD( char inValueBuf[], dword valueBufSize );
```

## Description

The function converts a string into a dword value. The string contains either a decimal value, e.g. "1234" and "-1234" or a hexadecimal value, e.g. "0x4321". The prefix 0x is automatically detected and the function converts the string.

## Parameters

- **inValueBuf[]**: Buffer containing the string.
- **valueBufSize**: Buffer size in byte of **inValueBuf**.

## Return Values

Converted string as dword value.

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)