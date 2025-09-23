[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetSchema.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Simulation Control](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » [Shared Functions](../CAPLFunctionsSmartChargingOverview.md#SimulationControl) » **SCC_SetSchema**

# SCC_SetSchema

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SetSchema ( char Namespace[] )
void SCC_SetSchema ( char Namespace[], long VersionMajor, long VersionMinor )
```

## Description

Sets the preferred schema version, corresponding to `<SchemaNamespace>` and optionally a specific version, in the XML configuration file.

The configured schema will be used unless a different one is derived from the **SupportedAppProtocol** handshake, and it will be prioritized during the handshake. If unspecified, the latest schema will have the highest priority.

When no version numbers are specified, depending on the context, it will mean **any** or **latest** version.

## Parameters

- **SchemaNamespace**: Desired namespace.
- **SchemaVersionMajor**: Desired major version number, may be -1 for EVSE simulation.
- **SchemaVersionMinor**: Desired minor version number, may be -1 for EVSE simulation.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
