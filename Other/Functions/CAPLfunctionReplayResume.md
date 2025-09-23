# ReplayResume

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword ReplayResume (char pName[]);
```

## Description

Starts the Replay Block with the name **pName** after it is suspended by [ReplaySuspend](CAPLfunctionReplaySuspend.md).

## Parameters

- **pName**: Name of the Replay Block.

## Return Values

- **1**: If successful
- **0**: If the Replay Block does not exist or cannot be restarted

## Example

See [ReplayResume](CAPLfunctionsExampleReplay.md)
