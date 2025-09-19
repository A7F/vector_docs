[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetDCEVStatus.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Data Queries](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueries) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GDataQueriesEVSE) » **SCC_GetDC_EVStatus**

# SCC_GetDC_EVStatus

**Valid for**:  CANoe DE • CANoe4SW DE

**Note**  
This function can be called only within the assigned callback. The function is used to query the details of a request.

## Function Syntax

```plaintext
void SCC_GetDC_EVStatus ( long& EVReady,
long& EVCabinConditioning,
long& EVRESSConditioning, char EVErrorCode[],
long& EVRESSSOC) // form 1
```

```plaintext
void SCC_GetDC_EVStatus ( long& EVReady, char EVErrorCode[], long& EVRESSSOC) // form 2
```

## Description

Gets the elements of **DC_EVStatus** (DIN/ISO) of a received DC message.

## Parameters

### Form 1

- **EVReady**: Gets the EVReady parameter of the DC status (via reference).
- **EVCabinConditioning**: Gets the EVCabinConditioning parameter of the DC status (via reference).
- **EVRESSConditioning**: Gets the EVRESSConditioning parameter of the DC status (via reference).
- **EVErrorCode**: Queries the EVRESSConditioning parameter of the DC status, if contained in the message (to the given char buffer).
- **EVRESSSOC**: Gets the EVRESSSOC parameter of the DC status (via reference).

### Form 2

- **EVReady**: Gets the EVReady parameter of the DC status (via reference).
- **EVErrorCode**: Queries the EVRESSConditioning parameter of the DC status if contained in the message (to the given char buffer).
- **EVRESSSOC**: Gets the EVRESSSOC parameter of the DC status (via reference).

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
