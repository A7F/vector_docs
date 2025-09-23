[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCTCPConnectInd.md)

# SCC_TCPConnectInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_TCPConnectInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_TCPConnectInd ( dword Port, long IsInitiator )
```

## Description

The callback is called when a TCP connection is opened.

## Parameters

- **Port**: Port number of the TCP connection.
- **IsInitiator**:
  - 1 if the node layer initiated the connection (client case).
  - 0 if the node layer received the connection request (server case).

## Return Values

—

## Example

—
