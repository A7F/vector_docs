[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPaymentServiceSelectionReq.md)

## SCC_PaymentServiceSelectionReq

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_PaymentServiceSelectionReq**

### Function Syntax

```plaintext
void SCC_PaymentServiceSelectionReq ( byte SessionID[], char SelectedPaymentOption[], long ServiceListCount )
```

### Description

The callback is called as soon as a Payment Service Selection Request is received. The Request contains the selected services and the chosen method of payment. Further details that are transmitted in this request can be queried with the following functions:

- [SCC_GetSelectedServiceID](../Functions/CAPLfunctionSCCGetSelectedServiceID.md)
- [SCC_GetSelectedParameterSetID](../Functions/CAPLfunctionSCCGetSelectedParameterSetID.md)

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **SelectedPaymentOption**: The selected payment option in form of a string.
- **ServiceListCount**: Number of selected services: Up to 8 entries are contained in the list. The list entries must be queried via separate help functions.

### Return Values

—

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)