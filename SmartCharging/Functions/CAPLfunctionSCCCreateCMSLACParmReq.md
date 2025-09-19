[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSLACParmReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateCM_SLAC_Parm_Req**

# SCC_CreateCM_SLAC_Parm_Req

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_SLAC_Parm_Req ( byte RunId[], byte SourceMac[], byte TargetMac[]
```

## Description

Creates a **CM_Slac_Parm.Req** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.

### Additional Parameters

1. **ApplicationType** (dword)
   - `0x00`: PEV-EVSE Association
   - `0x01-0xFF`: Reserved

2. **SecurityType** (dword)
   - `0x00`: No Security
   - `0x01`: Public Key Signature
   - `0x02-0xFF`: Reserved

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
