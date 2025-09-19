[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCableCheckReqIso.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **V2G Test Functions** » **Shared Functions** » **SCC_CreateCableCheckReq_ISO**

# SCC_CreateCableCheckReq_ISO

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateCableCheckReq_ISO 
( byte SessionID[], byte StatusFlags[], 
char ErrorCode[] )
```

## Description

Creates a Cable Check Request message for sending.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 - 0xFF FF FF FF FF FF FF FF.
- **StatusFlags**: Flags for DC_EVStatus:
  - StatusFlags[0] = EVReady
  - StatusFlags[1] = EVCabinConditioning
  - StatusFlags[2] = EVRESSConditioning
  - StatusFlags[3] = EVRESSSOC.
- **ErrorCode**: EVErrorCode for DC_EVStatus.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
