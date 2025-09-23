[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMAttenProfileInd.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateCM_Atten_Profile_Ind**

# SCC_CreateCM_Atten_Profile_Ind

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_Atten_Profile_Ind 
( byte SourceMac[], byte TargetMac[], 
byte PEVMAC[], dword NumGroups, byte AAG[] )
```

## Description

Creates a **CM_Atten_Profile.Ind** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **PEVMAC**: PEV MAC Address.
- **NumGroups**: Number of attenuation groups.
- **AAG**: Average Attenuation Group (array length is indicated by the parameter **NumGroups**).

### Additional Parameters

- **Index**: 0
- **Name**: Reserved field
- **Type**: dword
- **Description**: 1 byte

## Return Values

—

## Example

—
