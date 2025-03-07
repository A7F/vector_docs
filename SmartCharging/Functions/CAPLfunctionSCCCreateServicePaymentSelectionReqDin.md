[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateServicePaymentSelectionReqDin.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2GTestDIN) » SCC_CreateServicePaymentSelectionReq_DIN

# SCC_CreateServicePaymentSelectionReq_DIN

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateServicePaymentSelectionReq_DIN 
( byte SessionID[], 
char SelectedPaymentOption[], 
byte SelectedServiceIDs[], 
byte SelectedParameterSetIDs[], 
dword ServiceIDCount ); // form 1: deprecated
```

```plaintext
long SCC_CreateServicePaymentSelectionReq_DIN 
( byte SessionID[], 
char SelectedPaymentOption[], 
word SelectedServiceIDs[], 
int SelectedParameterSetIDs[], 
dword ServiceIDCount ); // form 2
```

## Description

Creates a Service Payment Selection Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **SelectedPaymentOption**: **Contract** or **ExternalPayment**.
- **SelectedServiceIDs**: IDs of the selected services. Must contain at least one entry.
- **SelectedParameterSetIDs**: Parameter set IDs corresponding to the SelectedServiceIDs. Array must be the same size as SelectedServiceIDs, you can use -1 to omit a parameter set ID.
- **ServiceIDCount**: Size of the array SelectedServiceIDs.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)