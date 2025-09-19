[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCInvalidMessageInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_InvalidMessageInd

# SCC_InvalidMessageInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_InvalidMessageInd ( long MessageType, long ErrorCode )
```

## Description

The callback is called when a SDP or V2G message is received with an invalid content (i.e. it is rejected by the session layer).

## Parameters

- **MessageType**: Type of the invalid message:
  - 0: SDP (SECC Discovery Protocol)
  - 1: V2G (Vehicle2Grid)

- **ErrorCode**: Type of error:
  - 0: Wrong version number, or version number format
  - 1: Unknown payload type
  - 2: Invalid payload length
  - 3: Error while decoding (EXI or XML parsing failed) – V2G only
  - 4: Invalid signature – V2G only

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
