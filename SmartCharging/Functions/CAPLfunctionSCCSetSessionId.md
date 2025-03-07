[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetSessionId.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Simulation Data** » **EVSE Functions** » **SCC_SetSessionId**

# SCC_SetSessionId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_SetSessionId (byte sessionId[])
```

## Description

Sets the new Session ID during the callback [SCC_SessionSetupReq](../Callbacks/CAPLfunctionSCCSessionSetupReq.md).

## Parameters

- **SessionId**: 8-byte long SessionID of the connection, range: 0 - 0xFF FF FF FF FF FF FF FF.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)