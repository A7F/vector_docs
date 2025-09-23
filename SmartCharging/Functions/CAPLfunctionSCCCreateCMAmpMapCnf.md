[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMAmpMapCnf.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateCM_Amp_Map_Cnf**

# SCC_CreateCM_Amp_Map_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_Amp_Map_Cnf ( byte SourceMac[], byte TargetMac[], dword ResType )
```

## Description

Creates a CM_Amp_Map.Cnf message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **ResTyp**:
  - 0x00 = Success
  - 0x01 = Failure

## Return Values

—

## Example

—
