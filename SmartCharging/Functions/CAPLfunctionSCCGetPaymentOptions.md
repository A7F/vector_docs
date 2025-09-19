# SCC_GetPaymentOptions

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetPaymentOptions.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEV) » SCC_GetPaymentOptions

**Valid for**: CANoe DE • CANoe4SW DE

## Note
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```
long SCC_GetPaymentOptions ( )
```

## Description

Gets the Payment options where 0=ExternalPayment, 1=Contract and 2=both

## Parameters

—

## Return Values

Available PaymentOptions, where the following applies:

- **0**: ExternalPayment
- **1**: Contract
- **2**: both

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
