[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetPreparedMsgFaultNotification.md)

## SCC_SetPreparedMsgFaultNotification

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Test Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#TestFunctions) » SCC_SetPreparedMsgFaultNotification

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

### Function Syntax

```plaintext
long SCC_SetPreparedMsgFaultNotification( char FaultCode[], char FaultMessage[] )
```

### Description

Sets the fault code and fault message for a prepared message.

### Parameters

- **FaultCode**: Desired fault code, which must be a valid enum value according to the specification.
- **FaultMsg**: Desired fault message string. If this string is empty, the optional message element is omitted.

### Return Values

- **0**: Not successful
- **1**: Successful

### Example

—
