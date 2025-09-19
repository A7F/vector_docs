[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionStartSimulation.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » StartSimulation

# StartSimulation

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
MethodReturnValueType StartSimulation ( )
```

## Description

This function activates the StateMachine of the EV/EVSE it is called on.

## Parameters

—

## Return Values

### MethodReturnValueType

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
