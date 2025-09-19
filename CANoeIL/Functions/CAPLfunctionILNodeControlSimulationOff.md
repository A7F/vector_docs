# ILNodeControlSimulationOff

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Note
- This function is not available for all OEM add-ons — depends on the CANoeIL.
- This function can be used in a global node outside the node context of the IL and in test modules.

## Function Syntax

```
long ILNodeControlSimulationOff(char aNodeName[])
```

## Description
Stops the simulation of the interaction layer of the specified simulation node. In this state, the interaction layer does not react on any function besides turning the simulation on again. The specified node must be in the current bus context. In all other cases, the function has no effect and will return with an error.

## Parameters
- **aNodeName**: Name of the node of which the interaction layer should be turned off.

## Return Values
- **0**: No error
- **-10000**: Unspecific error
- **-10001**: Node or module not found
- **-10002**: No suitable module available
- **-10003**: Function is not supported by module
- **-10004**: Module returns illegal value
- **other**: Error in module

## Example
—
