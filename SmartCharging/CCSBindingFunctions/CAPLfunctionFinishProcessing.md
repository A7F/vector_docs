[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionFinishProcessing.md)

## FinishProcessing

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » FinishProcessing

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

`MethodReturnValueType FinishProcessing ( )`

### Description

This function finishes the current **Ongoing** loop with a **Finished** message.

This method is available for the following embedded members:

- ISO20
- ScheduleRenegotiation

### Parameters

—

### Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0` OK
- `1` InvalidArgument
- `2` NoMatchingElementFound
- `3` UnknownError

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
