[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SmartCharging/Callbacks/CAPLfunctionSCCStateTransitionInd.md)

**CAPL Functions** » [Smart Charging](../CAPLFunctionsSmartChargingOverview.md) » [SCC Modeling Libraries (Simulation Setup)](../CAPLFunctionsSmartChargingOverview.md#BMNodeayerDLL) » [Shared Callback Functions](../CAPLFunctionsSmartChargingOverview.md#Callback) » SCC_StateTransitionInd

# SCC_StateTransitionInd

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE  •  CANoe4SW DE

## Function Syntax

```plaintext
void SCC_StateTransitionInd ( byte SessionID[], dword OldState, dword NewState )
```

## Description

The callback is called each time the internal state machine switches its state, i.e. usually when a new message is received. Use [SCC_GetStateName](../Functions/CAPLfunctionSCCGetStateName.md) for a string representation of the state IDs.

## Parameters

- **SessionID**: 8-byte long SessionID of SCC connection, range: 0 – 0xFF FF FF FF FF FF FF FF.
- **OldState**: Enum value of previous state.
- **NewState**: Enum value of new state.

## Return Values

—

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
