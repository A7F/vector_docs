[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetOptionalParameterFromConfig.md)

## SCC_SetOptionalParameterFromConfig

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **Test Functions** » **Shared Functions** » SCC_SetOptionalParameterFromConfig

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

`long SCC_SetOptionalParameterFromConfig ( dword Parameter, dword ConfigSection )`

### Description

Sets an optional parameter of type **complex** by referring to one of the **TestConfiguration** sections.

### Parameters

- **Parameter**: ID number of the parameter, as denoted in the lists of optional parameters below each Create-function.
- **ConfigSection**: ID of the config section where the parameter can be found.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
