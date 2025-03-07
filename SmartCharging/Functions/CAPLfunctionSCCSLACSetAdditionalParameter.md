[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSLACSetAdditionalParameter.md)

# SCC_SLAC_SetAdditionalParameter

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_SLAC_SetAdditionalParameter

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

Please make sure to use the correct value type and array length for the respective parameter. The parameter types are denoted in the lists of optional parameters below each Create-function.

## Function Syntax

```plaintext
long SCC_SLAC_SetAdditionalParameter ( dword Parameter, dword ParameterValue ) // form 1
long SCC_SLAC_SetAdditionalParameter ( dword Parameter, byte ParameterValues[] ) // form 2
```

## Description

Sets an additional parameter after creating a message, thus overwriting a value predefined by the specification (DIN 70121:2014-12).

## Parameters

- **Parameter**: ID number of the parameter, as denoted in the lists of optional parameters below each Create-function.
- **ParameterValue**: Desired value of the parameter in the matching data type.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)