[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANoeIL/Functions/CAPLfunctionILControlSimulationOn.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANoe IL](../CAPLfunctionsCANoeILOverview.md) » ILControlSimulationOn

# ILControlSimulationOn

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlSimulationOn](CAPLfunctionILNodeControlSimulationOn.md) can be used in a global node outside or in test modules.

## Function Syntax

```
long ILControlSimulationOn()
```

## Description

Start the simulation of the IL. The IL is in the same state as it was before stopping it by the function [ILControlSimulationOff](CAPLfunctionILControlSimulationOff.md).

## Parameters

—

## Return Values

- **0**: No error.
- **-1**: Momentary state of the IL does not permit this query.

## Example

—

[ILControlSimulationOff](CAPLfunctionILControlSimulationOff.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)