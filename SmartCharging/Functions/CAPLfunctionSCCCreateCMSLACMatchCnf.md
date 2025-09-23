[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSLACMatchCnf.md)

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » **SCC_CreateCM_SLAC_Match_Cnf**

# SCC_CreateCM_SLAC_Match_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CreateCM_SLAC_Match_Cnf ( byte RunId[], byte SourceMac[], byte TargetMac[], byte PEVMAC[], byte EVSEMAC[], byte NID[], byte NMK[] )
```

## Description

Creates a **CM_SLAC_Match.Cnf** message for sending.

## Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **PEVMAC**: PEV MAC Address.
- **EVSEMAC**: EVSE MAC Address.
- **NID**: Network ID given by the CCo (EVSE) (7 byte).
- **NMK**: Private NMK of the EVSE (random 16 byte value).

### Additional Parameters

1. **ApplicationType**:
   - Type: dword
   - Description:
     - `0x00 = PEV-EVSE Association`
     - `0x01-0xFF = Reserved`

2. **SecurityType**:
   - Type: dword
   - Description:
     - `0x00 = No Security`
     - `0x01 = Public Key Signature`
     - `0x02-0xFF = Reserved`

3. **MVFLength**:
   - Type: dword
   - Description: Length of the match variable field

4. **PEVID**:
   - Type: byte[]
   - Description: 17 byte ID

5. **EVSEID**:
   - Type: byte[]
   - Description: 17 byte ID

6. **Reserved field**:
   - Type: byte[]
   - Description: 8 byte

7. **Reserved field**:
   - Type: dword
   - Description: 1 byte

## Return Values

—

## Example

—
