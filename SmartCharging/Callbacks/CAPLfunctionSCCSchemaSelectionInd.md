[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCSchemaSelectionInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [EVSE Callback Functions](../CAPLFunctionsSmartChargingOverview.md#CallbackEVSE) » **SCC_SchemaSelectionInd**

# SCC_SchemaSelectionInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_SchemaSelectionInd ( char Namespace[], dword VersionMajor, dword VersionMinor )
```

## Description

Indicates that a schema has been chosen via the **SupportedAppProtoco** handshake.  
(The EVSE simulation automatically chooses a protocol from the vehicle’s list based on the priority.)

## Parameters

- **Namespace**: Namespace string of the selected schema.
- **VersionMajor**: Major version of the selected schema.
- **VersionMinor**: Major version of the selected schema.

## Return Values

—

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
