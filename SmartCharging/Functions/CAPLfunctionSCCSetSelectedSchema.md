[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Functions/CAPLfunctionSCCSetSelectedSchema.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [V2G Simulation Data](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » [EVSE Functions](../CAPLFunctionsSmartChargingOverview.md#V2GSimDataWrite) » **SCC_SetSelectedSchema**

# SCC_SetSelectedSchema

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
long SCC_SetSelectedSchema ( long SchemaID )
```

## Description

Sets the ID of the schema to be selected in the **SupportedAppProtocolRes** message. This overrides the automatic selection done based on the vehicle’s priority values.

**Note:** Due to technical reasons, the schema ID must belong to a schema actually offered by the vehicle (the charge point cannot continue with an undefined schema).

## Parameters

- **SchemaID**: ID of the selected schema, based on the vehicle’s list.

## Return Values

- **0**: Not successful
- **1**: Successful

## Example

—
