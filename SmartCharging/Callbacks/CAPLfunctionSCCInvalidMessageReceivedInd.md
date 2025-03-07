[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCInvalidMessageReceivedInd.md)

# InvalidMessageReceivedInd

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [CCS (Communication Setup)](../CAPLFunctionsSmartChargingOverview.md#BMCCS) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CCSCallback) » InvalidMessageReceivedInd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void InvalidMessageReceivedInd(InvalidMessageErrorType error);
```

## Description

The callback is called when a SDP or V2G message is received with an invalid format and is therefore not further processed. It is available for the whole Distributed Object.

## Parameters

- **error**: Type of error:
  - 0: Wrong version number or inverse version number
  - 1: Unknown payload type
  - 2: Invalid payload length

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)