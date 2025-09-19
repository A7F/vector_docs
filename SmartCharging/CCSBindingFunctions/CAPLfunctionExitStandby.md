[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionExitStandby.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » ExitStandby

# ExitStandby

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType ExitStandby ( )
```

## Description

This function instructs the EV to exit the **Standby** procedure by sending a Power Delivery Request with ChargeProgress set to **Start**. If the EV is not currently in the **Standby** procedure, calling this function will have no effect and will generate a warning.

**Note**: The EVSE may choose to not allow entering the **Standby** procedure, by replying with a **WARNING_StandbyNotAllowed** ResponseCode in the Power Delivery Response message. This function will not have any effect except for a warning in the **Write** window, if that happens.

## Parameters

—

## Return Values

**MethodReturnValueType**

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- `0` OK
- `1` InvalidArgument
- `2` NoMatchingElementFound
- `3` UnknownError

## Example

```plaintext
// To be called during 'Standby' procedure
on key 'c'
{
  EV.ISO20.ExitStandby.Call();
}
```

[EnterChargingSessionPauseOrStandby](CAPLfunctionEnterChargingSessionPauseOrStandby.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
