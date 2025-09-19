[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreatePaymentDetailsReqIso.md)

## SCC_CreatePaymentDetailsReq_ISO

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » SCC_CreatePaymentDetailsReq_ISO

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_CreatePaymentDetailsReq_ISO 
( byte SessionID[], dword ConfigSection, 
char ContractID[] ) // form 1
```

```plaintext
long SCC_CreatePaymentDetailsReq_ISO_AfterCertInstall ( byte SessionID [] ) // form 2
```

### Description

Creates a Payment Details Request message for sending.

Form 2 can be used to create a Payment Details Request using contract certificate chain of a previously received Certificate Installation or Update Response.

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ConfigSection**: Number of the section from the test configuration file to use.
- **ContractID**: ID string of the contract (eMAID).

### Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
