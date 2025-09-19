[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCTLSHandshakeInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » **SCC_TLSHandshakeInd**

# SCC_TLSHandshakeInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_TLSHandshakeInd( long Status, long IsServer)
```

## Description

The callback is called when a TLS handshake has been attempted after the SECC Discovery procedure. It is not called, however, if TLS is disabled or TCP was negotiated during SECC Discovery.

To enable TLS, call `SCC_SetTLSEnabled(1)` in CAPL or set the parameter `<UseTLS>` to 1 in the XML configuration file.

## Parameters

- **Status**
  - 1 – TLS handshake has successfully been completed.
  - 2 – TLS handshake has failed. The Write window may contain more details about the cause of the failure.
  - 3 – TLS handshake has most likely failed due to a bad certificate.

- **IsServer**
  - 0 – Callback for EV.
  - 1 – Callback for EVSE.
  - You may usually ignore this parameter as your CAPL code is linked to the EV or EVSE simulation DLL.

## Return Values

—

## Example

```c
void SCC_TLSHandshakeInd( long Status, long IsServer)
{
  WriteLineEx( 0, 0, "SCC_TLSHandshakeInd: status = %i, server = %i", Status, IsServer);
}
```

[SCC_TCPConnectInd](CAPLfunctionSCCTCPConnectInd.md)  •  [SCC_SetTLSEnabled](../Functions/CAPLfunctionSCCSetTLSEnabled.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
