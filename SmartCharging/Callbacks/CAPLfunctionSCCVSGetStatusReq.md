[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCVSGetStatusReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **Shared Callback Functions** » **SCC_VS_Get_Status_Req**

# SCC_VS_Get_Status_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_VS_Get_Status_Req(byte SourceMAC[])
```

## Description

This callback is called when a VS_Get_Status.Req message (from a VertexCom PLC chip) is received.

## Parameters

- **SourceMac**: The MAC address of the sender.

## Return Values

—

## Example

—

[SCC_VS_Get_Status_Cnf](CAPLfunctionSCCVSGetStatusCnf.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
