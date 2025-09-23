[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCPreSendInd.md)

## SCC_PreSendInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » SCC_PreSendInd

**Valid for:** CANoe DE • CANoe4SW DE

### Note

- Only the parameters listed below can be overwritten during a PreSend indication. If any other parameter is changed, it will not be applied until the next message is sent.

### Function Syntax

```plaintext
void SCC_PreSendInd ( byte SessionID[], dword MessageID, char ResponseCode[] )
```

### Description

The callback is called in active mode before a response message is sent. It enables checking the message’s response code and, if desired, overwriting it with another value. Additionally, overwriting the following parameters is supported:

- **EVSEStatusCode**
- **EVSEIsolationStatus**

### Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **[MessageID](SCC_MessageID.md)**: Type of message to be sent.
- **ResponseCode**: Response code string of the message. The list of possible response codes you find on page [SCC_SetResponseCode](../Functions/CAPLfunctionSCCSetResponseCode.md).

### Return Values

—

### Example

—
