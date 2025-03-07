[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/CCSBindingFunctions/CAPLfunctionSLACFinishedInd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » SLACFinishedInd

# SLACFinishedInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void SLACFinishedInd ( SLACFinishedIndType SlacResult )
```

## Description

This callback is called as soon as the state of SLACFinished changes.

## Parameters

- **SlacResult**: Enum with following values:
  - Fail = 1
  - FullyFinished = 2

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)