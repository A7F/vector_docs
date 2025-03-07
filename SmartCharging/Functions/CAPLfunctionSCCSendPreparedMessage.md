[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSendPreparedMessage.md)

## SCC_SendPreparedMessage

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_SendPreparedMessage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

**Note**

- If multiple Create-functions are called without using `SCC_SendPreparedMessage()` in between, all prior messages are discarded. Only the last created message is available for sending.
- Only messages that shall be signed according to the ISO 15118 specification may be sent as signed message. For all other messages, there is no difference between the two function calls.
- It is not allowed to call `SCC_SendPreparedMessage()` from within the [`SCC_MessageTxInd()`](../Callbacks/CAPLfunctionSCCMessageTxInd.md) callback. An attempt to do so will cause `SCC_SendPreparedMessage()` to return false and a warning will be output to the Write window. If you want to send a prepared message upon reception of `SCC_MessageTxInd()` please use a timer to defer the call. Please also be aware to avoid any recursions.

### Function Syntax

```plaintext
long SCC_SendPreparedMessage() // form 1
long SCC_SendPreparedMessage(dword ConfigSection) // form 2
```

### Description

Sends a message created using one of the Create-functions. Use the function call with parameter **ConfigSection** to create a signed message using the certificate name from the XML config. Else an unsigned message is sent.

### Parameters

- **ConfigSection**: ID of the config section where the certificates can be found.

### Return Values

- **1**: Successful
- **0**: Not successful

### Example

—