[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionSetNextEVSENotification.md)

## SetNextEVSENotification

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetNextEVSENotification

**Valid for**: CANoe DE • CANoe4SW DE

### Function Syntax

```
MethodReturnValueType SetNextEVSENotification ( EVSENotificationType EVSENotification )
```

### Description

This function overwrites the next **EVSENotification** value sent.

### Parameters

- **EVSENotification**: Enum with following values:
  - Pause = 0
  - ExitStandby = 1
  - Terminate = 2
  - ScheduleRenegotiation = 3
  - ServiceRenegotiation = 4
  - MeteringConfirmation = 5

### Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

### Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)