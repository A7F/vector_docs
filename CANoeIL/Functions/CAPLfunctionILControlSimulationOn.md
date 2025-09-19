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
