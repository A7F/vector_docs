[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPSetPollingCycle.md)

[CAPL Functions](../../CAPLfunctions.md) » [XCP](../CAPLfunctionsXCPOverview.md) » xcpSetPollingCycle

# xcpSetPollingCycle

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long xcpSetPollingCycle(char namespace[], char variable[], long cycleTime); // form 1
long xcpSetPollingCycle(sysvar sysvar, long cycleTime); // form 2
```

## Description

Sets the cycle time of a parameter, if the read mode of the parameter is set to **polling**.

## Parameters

- **namespace**: Namespace of the corresponding system variable.
- **variable**: Name of the corresponding system variable.
- **sysvar**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysvar::"
- **cycleTime**: Cycle time with which the parameter is measured.

## Return Values

- **0**: OK
- **-1**: System variable of the parameter was not found
- **-2**: Operation not allowed

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)