[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateCMSetKeyReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [SLAC Test Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SLACtest) » SCC_CreateCM_Set_Key_Req

# SCC_CreateCM_Set_Key_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```c
void SCC_CreateCM_Set_Key_Req ( byte SourceMac[], byte TargetMac[], byte NID[], byte NMK[] )
```

## Description

Creates a **CM_Set_Key.Req** message for sending.

## Parameters

- **SourceMac**: Source address of the Ethernet packet.
- **TargetMac**: Destination address of the Ethernet packet.
- **NID**: Network ID given by the CCo (EVSE) (7 byte).
- **NMK**: NMK to be set (16 byte).

### Additional Parameters

1. **KeyType** (dword):
   - 0x00 = DAK (AES-128)
   - 0x01 = NMK (AES-128)
   - 0x02 = NEK (AES-128)
   - 0x03 = TEK (AES-128)
   - 0x04 = Hash Key (Random-3072)
   - 0x05 = Nonce Only (no key)
   - 0x06-0xFF = Reserved

2. **MyNonce** (byte[]): 4 byte random number.
3. **YourNonce** (byte[]): Last received nonce (4 byte).
4. **PID** (dword): Protocol ID.
5. **PRN** (byte[]): Protocol Run Number (2 byte).
6. **PMN** (dword): Protocol Message Number.
7. **CCoCapability** (dword): STA’s CCo Capability.
8. **NewEKS** (dword): PEKS or EKS.

## Return Values

—

## Example

—

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
