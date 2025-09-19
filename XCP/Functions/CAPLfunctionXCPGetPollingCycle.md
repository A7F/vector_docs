[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/XCP/Functions/CAPLfunctionXCPGetPollingCycle.md)

**CAPL Functions** » **XCP** » **xcpGetPollingCycle**

# xcpGetPollingCycle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long xcpGetPollingCycle(char namespace[], char variable[]); // form 1`
- `long xcpGetPollingCycle(sysvar sysvar); // form 2`

## Description

Returns the cycle time of a parameter, if the read mode of the parameter is set to **polling**.

## Parameters

- **namespace**: Namespace of the corresponding system variable.
- **variable**: Name of the corresponding system variable.
- **sysvar**: Name of the fully qualified name of the system variable, including all namespaces, separated by "::". The name must be preceded by "sysvar::".

## Return Values

- **> 0**: Cycle time
- **-1**: System variable of the parameter was not found
- **-2**: Operation not allowed

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
