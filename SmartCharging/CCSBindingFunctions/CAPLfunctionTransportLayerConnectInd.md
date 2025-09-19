[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionTransportLayerConnectInd.md)

## TransportLayerConnectInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » TransportLayerConnectInd

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
void TransportLayerConnectInd ( uint32 Port, bool TLS )
```

### Description

This callback is called as soon as the TransportLayer is connected. In case of a TLS connection the callback is called twice, once for TCP and once for TLS, indicated by the corresponding parameter.

### Parameters

- **Port**: Port number of the TCP connection
- **TLS**:
  - 1 if TLS is used.
  - 0 if TLS is not used.

### Return Values

—

### Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
