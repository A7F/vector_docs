[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetOptionalParameter.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » **SCC_SetOptionalParameter**

# SCC_SetOptionalParameter

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**  
Please make sure to use the correct value type for the respective parameter; e.g. an integer will not be automatically converted to a string if the parameter type is char[]. For float parameters, use float notation (e.g. **0.0**, **12.8**). The parameter types are denoted in the lists of optional parameters below each Create-function.

## Function Syntax

- `long SCC_SetOptionalParameter ( dword Parameter, long ParameterValue ) // form 1`
- `long SCC_SetOptionalParameter ( dword Parameter, float ParameterValue ) // form 2`
- `long SCC_SetOptionalParameter ( dword Parameter, char ParameterValue[] ) // form 3`
- `long SCC_SetOptionalParameter ( dword Parameter, byte ParameterValue[] ) // form 4`
- `long SCC_SetOptionalParameter ( dword Parameter, byte ParameterValue[], dword length ) // form 5`

## Description

Sets an optional parameter after creating a message.

Form 5 only copies the number of bytes specified by the length parameter. Only available for the **SigMeterReading** element.

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
