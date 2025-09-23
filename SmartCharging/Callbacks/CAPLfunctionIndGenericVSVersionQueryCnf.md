[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionIndGenericVSVersionQueryCnf.md)

## SCC_Generic_VS_VersionQuery_Cnf

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_Generic_VS_VersionQuery_Cnf

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```c
void SCC_Generic_VS_VersionQuery_Cnf(byte sourceMacAddress[], char versionString[]);
```

### Description

The callback is called as soon as a `VS_Get_Version.Cnf` or equivalent message is received. The `versionString` Parameter will be formatted based on the type of confirmation message received. The version can be requested by using the [SCC_CreateGenericVS_VersionQuery_Req](../Functions/CAPLfunctionCreateGenericVSVersionQueryReq.md) function.

Currently supported OUIs:

- Qualcomm (0x00B052)
- MStar, MediaTek and Vertexcom (0x0013D7)
- Lumissil (0x0016E8)

### Parameters

- **SourceMacAddress**: MAC address of sender.
- **versionString**: Version string formatted based on the type of chip that answers the request.

### Return Values

—

### Example

—

[SCC_CreateGenericVS_VersionQuery_Req](../Functions/CAPLfunctionCreateGenericVSVersionQueryReq.md)
