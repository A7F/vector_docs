[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateServiceDetailReqIso.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » **SCC_CreateServiceDetailReq_ISO**

# SCC_CreateServiceDetailReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateServiceDetailReq_ISO 
( byte SessionID[], dword ServiceId )
```

## Description

Creates a Service Detail Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **ServiceId**: ID of the requested service.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
