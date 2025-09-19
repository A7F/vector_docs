[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMAmpMapReq.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_CM_Amp_Map_Req

# SCC_CM_Amp_Map_Req

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_CM_Amp_Map_Req(byte RunId[], byte SourceMac[], dword AmLen, byte AmData[])
```

## Description

The callback is called as soon as a `CM_Amp_Map.Req` message is received.

## Parameters

- **RunId**: 8-byte long run ID.
- **SourceMac**: MAC address of sender.
- **AmLen**: Length of the AmData array.
- **AmData**: Power spectral density difference values as defined by the specification. **Note**: Because the PSD is defined in values of 4 bit, only the lower half of each byte is considered.

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
