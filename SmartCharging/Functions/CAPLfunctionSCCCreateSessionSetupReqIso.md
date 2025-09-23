[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSessionSetupReqIso.md)

### CAPL Functions » Smart Charging » SCC Modeling Libraries (Simulation Setup) » V2G Test Functions » Shared Functions » SCC_CreateSessionSetupReq_ISO

# SCC_CreateSessionSetupReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateSessionSetupReq_ISO 
( byte SessionID[], byte EVCCID[] )
```

## Description

Creates a Session Setup Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **EVCCID**: 6 byte long ID of the vehicle (MAC address).

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—
