[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSupportedAppProtocolReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » **SCC_CreateSupportedAppProtocolReq**

# SCC_CreateSupportedAppProtocolReq

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_CreateSupportedAppProtocolReq ( dword ConfigSection )
```

## Description

Creates a **SupportedAppProtocol** Request message for sending.

## Parameters

- **ConfigSection**: Number of the section from the test configuration file to use.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
