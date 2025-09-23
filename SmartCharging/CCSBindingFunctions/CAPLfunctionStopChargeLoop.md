[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionStopChargeLoop.md)

## StopChargeLoop

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » StopChargeLoop

### Tool Availability

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

```plaintext
MethodReturnValueType StopChargeLoop ()
```

### Description

This function finished the ChargeLoop by sending the next message in the communication workflow.

### Parameters

—

### Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

### Example

—
