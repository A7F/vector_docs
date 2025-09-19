[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetOptionalParameterUnsigned.md)

# SCC_SetOptionalParameterUnsigned

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_SetOptionalParameterUnsigned

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**

Parameters marked as **long** or **dword** can all be accessed both with this function and with [SCC_SetOptionalParameter (dword, long)](CAPLfunctionSCCSetOptionalParameter.md). Usage of this function is only mandatory if the whole 32 bit unsigned number range is needed.

## Function Syntax

```
long SCC_SetOptionalParameterUnsigned 
( dword Parameter, dword ParameterValue )
```

## Description

Sets an optional parameter using a DWORD value after creating a message.

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
