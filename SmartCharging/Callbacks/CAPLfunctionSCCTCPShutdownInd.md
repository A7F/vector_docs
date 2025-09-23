[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCTCPShutdownInd.md)

# SCC_TCPShutdownInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_TCPShutdownInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_TCPShutdownInd ( dword Port, long IsInitiator )
```

## Description

The callback is called when a TCP connection is closed.

## Parameters

- **Port**: Port number of the TCP connection.
- **IsInitiator**:
  - 1 if the node layer initiated the shutdown.
  - 0 if the node layer received the shutdown request.

## Return Values

—

## Example

—
