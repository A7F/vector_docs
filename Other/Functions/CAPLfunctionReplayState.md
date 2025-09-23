# ReplayState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword ReplayState (char pName[]);
```

## Description

Returns the state of the Replay Block with the name **pName**.

## Parameters

- **pName**: Name of the Replay Block

## Return Values

- **0**: Replay Block is stopped (state: stopped)
- **1**: Execution of the Replay file was started (state: running)
- **2**: Execution of the Replay file was stopped (state: suspended)
- **(dword)-1**: when the Replay Block does not exist

## Example

See [ReplayState](CAPLfunctionsExampleReplay.md)
