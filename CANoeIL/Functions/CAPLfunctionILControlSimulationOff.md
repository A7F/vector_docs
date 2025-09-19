# ILControlSimulationOff

**Valid for**: CANoe DE • CANoe4SW DE

**Note**: This function can only be used in the CAPL file that is attached to the appropriate node. The corresponding function [ILNodeControlSimulationOff](CAPLfunctionILNodeControlSimulationOff.md) can be used in a global node outside or in test modules.

## Function Syntax

```
long ILControlSimulationOff()
```

## Description

The simulation of the IL is stopped. After that no other function to control the IL has an effect to the IL.

To restart the simulation of the IL use [ILControlSimulationOn](CAPLfunctionILControlSimulationOn.md).

## Parameters

—

## Return Values

- **0**: No error.

## Example

—

[ILControlSimulationOn](CAPLfunctionILControlSimulationOn.md)
