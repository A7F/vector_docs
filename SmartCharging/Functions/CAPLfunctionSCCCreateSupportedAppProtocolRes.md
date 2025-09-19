[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCCreateSupportedAppProtocolRes.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Test Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#V2Gtestfunctions) » SCC_CreateSupportedAppProtocolRes

# SCC_CreateSupportedAppProtocolRes

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_CreateSupportedAppProtocolRes ( char ResponseCode[] )
```

## Description

Creates a SupportedAppProtocol Response message for sending.

## Parameters

- **ResponseCode**: Acknowledgment status of the message. The list of possible response codes you find on page [SCC_SetResponseCode](CAPLfunctionSCCSetResponseCode.md).

### Optional Parameters

- **Index**: 0
- **Name**: SchemaId
- **Type**: long
- **Description**: Unique ID of one of the vehicle’s supported protocols.

## Return Values

- **1**: If successful.
- **0**: Else (message cannot be sent).

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
