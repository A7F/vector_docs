[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCVSHostActionInd.md)

## SCC_VS_HostAction_Ind

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_VS_HostAction_Ind

**Valid for**:  CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_VS_HostAction_Ind ( byte SourceMacAddess[], dword hostActionReq )
```

### Description

The callback is called as soon as a `VS_Host_Action.Ind` message is received. This indication is enabled only in QCA7000/QCA7005 device with SLAC enabled configuration. (Additional data cannot be queried at the moment.)

### Parameters

- **SourceMacAddress**: MAC address of sender.
- **hostActionReq**: Notification:
  - `QCA_HAR_READY_TO_JOIN_AVLN = 0x09`
  - `QCA_HAR_AVLN_JOINED = 0x0A`
  - `QCA_HAR_AVLN_DISCONNECTED = 0x0B`

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
