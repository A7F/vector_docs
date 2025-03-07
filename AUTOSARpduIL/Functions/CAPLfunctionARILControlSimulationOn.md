[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILControlSimulationOn.md)

**CAPL Functions** » [AUTOSAR PDU IL](../CAPLfunctionsAUTOSARpduILOverview.md) » ARILControlSimulationOn

# ARILControlSimulationOn

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILControlSimulationOn()
```

## Description

Starts the simulation of the IL. The IL is operational and started. The IL will send PDUs.

## Parameters

—

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlSimulationOff](CAPLfunctionARILControlSimulationOff.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)