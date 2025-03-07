[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMAmpMapReq.md)

## SCC_CreateCM_Amp_Map_Req

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **SLAC Test Functions** » **Shared Functions** » SCC_CreateCM_Amp_Map_Req

### Valid for: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_CreateCM_Amp_Map_Req ( byte SourceMac[], byte TargetMac[], dword AmLen, byte AmData[] )
```

### Description

Creates a CM_Amp_Map.Req message for sending.

### Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **AmLen**: Length of the AmData array.
- **AmData**: Power spectral density difference values as defined by the specification.  
  **Note**: Because the PSD is defined in values of 4 bit, only the lower half of each byte is considered.

### Return Values

—

### Example

—

© Vector Informatik GmbH  
**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)