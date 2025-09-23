[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCCMSLACMatchReq.md)

## SCC_CM_SLAC_Match_Req

**CAPL Functions** » **Smart Charging** » **SCC Modeling Libraries (Simulation Setup)** » **EVSE Callback Functions** » **SCC_CM_SLAC_Match_Req**

### Tool Availability
[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void SCC_CM_SLAC_Match_Req ( byte RunId[], byte SourceMacAddress[], byte PEVMacAddress[], byte EVSEMacAddress[] )
```

### Description
The callback is called as soon as a **CM_SLAC_Match.Req** message is received.

Further details that are transmitted in this request can be queried with the following functions:

- [SCC_SLAC_GetApplicationType](../Functions/CAPLfunctionSCCSLACGetApplicationType.md)
- [SCC_SLAC_GetSecurityType](../Functions/CAPLfunctionSCCSLACGetSecurityType.md)
- [SCC_SLAC_GetMVFLength](../Functions/CAPLfunctionSCCSLACGetMVFLength.md)
- [SCC_SLAC_GetPEVAndEVSEId](../Functions/CAPLfunctionSCCSLACGetPEVAndEVSEId.md)

### Parameters

- **RunId**: Random Run Identifier of sender (8 byte).
- **SourceMacAddress**: MAC address of sender.
- **PEVMacAddress**: MAC Address of the vehicle.
- **EVSEMacAddress**: MAC Address of the EVSE.

### Return Values
—

### Example
—
