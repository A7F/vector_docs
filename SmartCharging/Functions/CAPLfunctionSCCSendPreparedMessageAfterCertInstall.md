[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSendPreparedMessageAfterCertInstall.md)

# SCC_SendPreparedMessage_AfterCertInstall

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_SendPreparedMessage_AfterCertInstall

**Valid for:**  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SCC_SendPreparedMessage_AfterCertInstall ( )
```

## Description

Sends a message created using one of the Create-functions. The message is signed using the installed private key of a previous Certificate Installation or Certificate Update Response.

See also: [SCC_SendPreparedMessage](CAPLfunctionSCCSendPreparedMessage.md)

## Parameters

—

## Return Values

- **1**: Successful
- **0**: Not successful

## Example

—
