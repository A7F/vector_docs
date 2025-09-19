[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetTargetCurrent.md)

## SCC_SetTargetCurrent

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data** » **EV Functions** » **SCC_SetTargetCurrent**

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Note
This function needs a running SCC session in order to work. Make sure to call it only after the Session Setup Request message is sent.

### Function Syntax

```plaintext
long SCC_SetTargetCurrent ( float TargetCurrent )
```

### Description
Sets the desired current. These limits are used in various DC messages. If no values are set, the vehicle will automatically calculate defaults.

### Parameters
- **TargetCurrent**: Value to be set.

### Return Values
- **0**: Not successful
- **1**: Successful

### Example
—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
