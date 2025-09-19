[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionStartScheduleRenegotiation.md)

# StartScheduleRenegotiation

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#BMCCSEV) » StartScheduleRenegotiation

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType StartScheduleRenegotiation ();
```

## Description

This function is used to start the ScheduleRenegotiation process on EV side. The EVSE side can trigger the same process by using the [SetNextEVSENotification](CAPLfunctionSetNextEVSENotification.md) method.

The function is available for the following embedded members:

- ISO20

## Parameters

—

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0`: OK
- `1`: InvalidArgument
- `2`: NoMatchingElementFound
- `3`: UnknownError

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
