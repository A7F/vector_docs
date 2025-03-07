[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/AUTOSARpduIL/Functions/CAPLfunctionARILControlSimulationOff.md)

**CAPL Functions** » **AUTOSAR PDU IL** » **ARILControlSimulationOff**

# ARILControlSimulationOff

**Valid for**: CANoe DE • CANoe4SW DE

### Note

This function should not be used in the **on PreStart** event procedure.

## Function Syntax

```plaintext
long ARILControlSimulationOff()
```

## Description

Stops the simulation of the IL. The IL is not operational. All API function except function [ARILControlSimulationOn](CAPLfunctionARILControlSimulationOn.md) will not work.

## Parameters

—

## Return Values

- **0**: No error.
- **Others**: [Error](../../../CANoeCANalyzer/LibrariesPackages/AUTOSARpduIL/AUTOSARpduILReturnCodes.md) in module.

## Example

—

[ARILControlSimulationOn](CAPLfunctionARILControlSimulationOn.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)