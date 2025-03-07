[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILFaultInjectionSetPowerState.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILFaultInjectionSetPowerState**

# ARILFaultInjectionSetPowerState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Setting the ignition state with this function will not update the appropriate global system variable (`sysvar::_ILControl::Power`). Therefore the state of the local IL instance will only be affected. Afterwards changes of the global system variable or calling [ARILSetPowerState](CAPLfunctionARILSetPowerState.md) will have not any effect.

## Function Syntax

```plaintext
long ARILFaultInjectionSetPowerState (long value);
```

## Description

Activates or deactivates the power status locally. Modifying the power state of the local IL instance is similar to calling [ARILControlSimulationOn](CAPLfunctionARILControlSimulationOn.md) or [ARILControlSimulationOff](CAPLfunctionARILControlSimulationOff.md).

## Parameters

- **value**
  - 0: Set power state **off**.
  - 1: Set power state **on**.
  - -1: Disables the fault injection and sets the desired global state.

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)