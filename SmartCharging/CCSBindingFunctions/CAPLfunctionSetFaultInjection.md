[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionSetFaultInjection.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#CCSGeneral) » SetFaultInjection

# SetFaultInjection

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`MethodReturnValueType SetFaultInjection ( FaultInjectionType faultInjectionType, bool enable )`

## Description

Enables fault injection within the V2G communication.

## Parameters

- **faultInjectionType**: Enum with following values:
  - 0 = All (set all types below)
  - 1 = PreventTCPShutdown
  - 2 = PreventTCPShutdownReaction

- **enable**: 
  - 1 = enable
  - 0 = disable

## Return Values

### MethodReturnValueType

All function calls (except for indications) will return a MethodReturnValueType indicating whether the call was successful or not. Possible values:

- 0: OK
- 1: InvalidArgument
- 2: NoMatchingElementFound
- 3: UnknownError

## Example

—

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)