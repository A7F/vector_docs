[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetChargeProgress.md)

## SCC_GetChargeProgress

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data** » **EV Functions** » SCC_GetChargeProgress

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
long SCC_GetChargeProgress( )
```

### Description

Returns the charge progress of the vehicle, which is defined by the last transmitted **PowerDeliveryReq** message.

- For ISO 15118-2, **ChargeProgress** is an explicit message parameter, which is returned directly.
- For DIN 70121, the information is mapped to a **ChargeProgress** value accordingly.
- If no **PowerDeliveryReq** message has been sent yet, -1 is returned.

### Parameters

—

### Return Values

- **-1**: Initial
- **0**: Stop
- **1**: Start
- **2**: ReNegotiation

### Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
