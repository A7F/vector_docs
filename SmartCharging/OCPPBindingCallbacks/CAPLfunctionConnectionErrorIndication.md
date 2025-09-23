[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/OCPPBindingCallbacks/CAPLfunctionConnectionErrorIndication.md)

## ConnectionErrorIndication

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [OCPP](../CAPLFunctionsSmartChargingOverview.md#BMOCPP) » [Callback Functions](../CAPLFunctionsSmartChargingOverview.md#BMOCPPCallbackFunctions) » ConnectionErrorIndication

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void ConnectionErrorIndication(WebsocketConnectionErrorType error);
```

### Description

The callback is called when an error regarding the WebSocket connection occurred.

### Parameters

- **error**  
  Type of error:
  - 1: Error during TCP connection setup
  - 2: Wrong subprotocol in WebSocket handshake detected

### Return Values

—

### Example

—
