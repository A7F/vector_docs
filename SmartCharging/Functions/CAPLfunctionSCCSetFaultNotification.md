[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetFaultNotification.md)

## SCC_SetFaultNotification

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data** » **Shared Functions** » **SCC_SetFaultNotification**

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_SetFaultNotification ( char FaultCode[], char FaultMsg[] )
```

### Description

Sets the fault code and message for the next V2G message. The fault code is contained within the V2G header.

### Parameters

- **FaultCode**: Desired fault code, which must be a valid enum value according to the specification.
- **FaultMsg**: Desired fault message string. If this string is empty, the optional message element is omitted.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)