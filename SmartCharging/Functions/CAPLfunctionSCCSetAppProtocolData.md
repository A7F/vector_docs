[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetAppProtocolData.md)

# SCC_SetAppProtocolData

[CAPL Functions](../../CAPLfunctions.md) » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EV Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » SCC_SetAppProtocolData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetAppProtocolData(long ProtocolIndex, long Index, long Value);
```

## Description

Overwrite the fields **VersionNumberMajor**, **VersionNumberMinor**, **SchemaID** or **Priority** after a SupportedAppProtocolReq message has been created using [SCC_CreateSupportedAppProtocolReq](CAPLfunctionSCCCreateSupportedAppProtocolReq.md).

## Parameters

- **ProtocolIndex**: The index of the AppProtocol entry to be modified, starting at 0 (zero). An error will be returned if the index is invalid.
- **Index**: The index of the field in the selected AppProtocol. The following indices are defined:
  - 1: VersionNumberMajor
  - 2: VersionNumberMinor
  - 3: SchemaID
  - 4: Priority
  - Any other index will cause an error to be returned.
- **Value**: The new value for the selected field.

## Return Values

- `0`: error
- `1`: success

## Example

```plaintext
// create a SupportedAppProtocolReq message using test configuration with ID="2"
SCC_CreateSupportedAppProtocolReq(2);
// set the VersonNumberMinor of the first AppProtocol element to 1
SCC_SetAppProtocolData(0, 2, 1);
// send the modified message
SCC_SendPreparedMessage();
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
