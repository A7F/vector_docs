[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetResponseCodeString.md)

## SCC_GetResponseCodeString

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetResponseCodeString

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

### Note
This function can be called only within the assigned callback. The function is used to query the details of a request.

### Function Syntax

```
void SCC_GetResponseCodeString ( char ResponseCode[] )
```

### Description
Gets the response code.

The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).

### Parameters

- **ResponseCode**: Queries the Response code string (to the given char buffer). This allows for evaluating its actual semantics, whereas each callback only returns a binary value indicating **OK** or **FAILED**.

### Return Values
—

### Example
—
