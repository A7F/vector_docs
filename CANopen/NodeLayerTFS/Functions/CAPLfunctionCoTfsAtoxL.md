[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsAtoxL.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsatoxL**

# coTfsatoxL

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
This function should not be used in user specific CAPL programs.

## Function Syntax

```
long coTfsatoxL( char inValueBuf[], dword valueBufSize );
```

## Description

The function converts a string into a long value. The string contains either a decimal value, e.g. "1234" or a hexadecimal value, e.g. "0x4321". The prefix 0x is automatically detected and the function converts the string.

## Parameters

- **inValueBuf[]**: Buffer containing the string.
- **valueBufSize**: Buffer size in bytes of **inValueBuf**.

## Return Values

Converted string as long value.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)