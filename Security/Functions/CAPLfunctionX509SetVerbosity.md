[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionX509SetVerbosity.md)

# X509_SetVerbosity

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » X509_SetVerbosity

**Valid for**: CANoe DE • CANoe4SW DE

## Method Syntax

```plaintext
void  X509_SetVerbosity(dword level);
```

## Description

Configures the notification level of X509Certificate functions from off (0) to high (5).

## Parameters

- **dword level**  
  Desired notification level. Range: 0-5
  - 0: Off
  - 1: All errors are printed
  - 2: Additionally warnings are printed
  - 3: Information messages are printed too
  - 4-5: Debug messages are active

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
