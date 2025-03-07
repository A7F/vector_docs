[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCGetPreparedEXIMessage.md)

# SCC_GetPreparedEXIMessage

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_GetPreparedEXIMessage

**Valid for**:  CANoe DE • CANoe4SW DE

### Note

- Use this function to access the EXI encoder to create reference messages, or to create V2G messages with a custom TCP header. The latter can then be sent using the features of the [Option Ethernet](../../IP/CAPLfunctionsIPOverview.md).
- It is possible to call [SendPreparedMessage()](CAPLfunctionSCCSendPreparedMessage.md) subsequently without preparing the message anew.

## Function Syntax

```plaintext
long SCC_GetPreparedEXIMessage ( byte data[], dword& dataLength ) // form 1
long SCC_GetPreparedEXIMessage ( byte data[], dword& dataLength, dword ConfigSection ) // form 2
```

## Description

Finalizes a message without sending. The message data is returned to an output buffer instead. Usually this data consists of the V2G header and the EXI encoded V2G payload.

## Parameters

- **Data**: Queries the message (to the given byte buffer). Make sure to use a buffer that is large enough (some messages may take up to 10 kB).
- **DataLength**: Gets the length of the copied data (via reference).
- **ConfigSection**: ID of the config section where the certificates can be found.

## Return Values

The Id attribute of the message body, if existing (to the output buffer).

## Example

—