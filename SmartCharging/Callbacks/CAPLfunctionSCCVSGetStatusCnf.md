[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCVSGetStatusCnf.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » **SCC_VS_Get_Status_Cnf**

# SCC_VS_Get_Status_Cnf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_VS_Get_Status_Cnf(byte SourceMAC[], long Result, long Status, long LinkState, long Ready)
```

## Description

This callback is called when a VS_Get_Status.Cnf message (from a VertexCom PLC chip) is received.

The callback function [SCC_Generic_VS_HostMessage_Ind](CAPLfunctionIndGenericVSHostMessageInd.md) (byte sourceMacAddress[], dword hostMessageInd) will also be called immediately after this callback.

**Note**: Only the most relevant values from the VS_Get_Status.Cnf message are returned by this callback. Other values are currently not accessible by application code.

## Parameters

- **SourceMac**: The MAC address of the sender.
- **Result**: The "Result" value of the VS_Get_Status.Cnf message.
- **Status**: The "Status" value of the VS_Get_Status.Cnf message.
- **LinkState**: The "Link State" value of the VS_Get_Status.Cnf message.
- **Ready**: The "Ready for PLC operation" value of the VS_Get_Status.Cnf message.

## Return Values

—

## Example

—

[SCC_VS_Get_Status_Req](CAPLfunctionSCCVSGetStatusReq.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
