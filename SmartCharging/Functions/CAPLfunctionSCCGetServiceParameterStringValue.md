[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetServiceParameterStringValue.md)

# SCC_GetServiceParameterStringValue

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetServiceParameterStringValue

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_GetServiceParameterStringValue ( long i1, long i2, char Value[] )
```

## Description

Gets the **string value** of the parameter with the selected indices within a ServiceDetailRes message.

## Parameters

- **I1**: Selected index of a parameter set < ParameterSetCount.
- **I2**: Selected index of a parameter.
- **Value**: Queries the service name value (to the given char buffer).

## Return Values

—

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)