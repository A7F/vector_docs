[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCMessageTxInd.md)

# SCC_MessageTxInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_MessageTxInd

**Valid for**: CANoe DE • CANoe4SW DE

## Notes

- It is not allowed to call [SCC_SendPreparedMessage()](../Functions/CAPLfunctionSCCSendPreparedMessage.md) from within this callback. An attempt to do so will cause `SCC_SendPreparedMessage()` to return false and a warning will be output to the Write window.
- If you want to send a prepared message upon reception of this callback please use a timer to defer the call. Please also be aware to avoid any recursions.

## Function Syntax

```c
void SCC_MessageTxInd ( byte SessionOrRunID[], dword MessageID, long Error )
```

## Description

The callback is called each time a **Vehicle2Grid**, **SECC Discovery** or **SLAC** message is sent by the simulation DLL.

## Parameters

- **SessionOrRunID**: 8-byte long SessionID (V2G) or RunID (SLAC) of the connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **[MessageID](SCC_MessageID.md)**: Type of sent message:
  - For SLAC messages, MMType (2 byte) according to specification.
  - For V2G messages see help page [MessageID](SCC_MessageID.md).
- **Error**:
  - 0 if the sending was successful.
  - > 0 if the send call failed (sending may fail due to socket errors or the absence of a receiver which sends ACK packages).

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
