[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetServiceParameterData.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » **SCC_GetServiceParameterData**

# SCC_GetServiceParameterData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_GetServiceParameterData ( long i1, long i2, char Name[], char ValueType[] )
```

## Description

Gets the name and value type of the parameter with the selected indices.

## Parameters

- **i1**: Selected index of the target SAScheduleTuple (< TariffCount).
- **i2**: Selected index of the target SalesTariffEntry (< SalesTariffEntriesCount).
- **Name**: Queries the name of the parameter with the selected indices (to the given char buffer).
- **ValueType**: Queries the value type of the parameter with the selected indices (to the given char buffer).  
  For DIN 70121, ValueType is the actual content of the element `<ValueType>`. For ISO 15118, the subelement holding the parameter value is evaluated and ValueType is set accordingly. In both cases, there are the same possible results for ValueType, e.g. **int, physicalValue, string**.

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)