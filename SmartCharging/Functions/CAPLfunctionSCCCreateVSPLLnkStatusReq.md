[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateVSPLLnkStatusReq.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateVS_PL_Lnk_Status_Req**

# SCC_CreateVS_PL_Lnk_Status_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```c
void SCC_CreateVS_PL_Lnk_Status_Req ( byte SourceMac[], byte TargetMac[] )
```

## Description

Creates a **VS_PL_Lnk_Status.Req** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.

### Additional Parameters

- **Index**: 0
- **Name**: OUI
- **Type**: byte[]
- **Description**: 3 byte Organizationally Unique Identifier.

## Return Values

—

## Example

—
