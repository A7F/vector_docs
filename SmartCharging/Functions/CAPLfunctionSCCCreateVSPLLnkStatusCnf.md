[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateVSPLLnkStatusCnf.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateVS_PL_Lnk_Status_Cnf**

# SCC_CreateVS_PL_Lnk_Status_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateVS_PL_Lnk_Status_Cnf 
( byte SourceMac[], byte TargetMac[], 
dword MStatus, dword LinkStatus )
```

## Description

Creates a **VS_PL_Lnk_Status.Cnf** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **MStatus**: MME Status:
  - 0x00 = success
  - 0xFF = failure
- **LinkStatus**: Indicates if a link is established:
  - 0x00 = no link
  - 0x01 = link

### Additional Parameters

| Index | Name | Type   | Description                                 |
|-------|------|--------|---------------------------------------------|
| 0     | OUI  | byte[] | 3 byte Organizationally Unique Identifier.  |

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)