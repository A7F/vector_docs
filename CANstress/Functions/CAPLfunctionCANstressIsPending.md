# CANstressIsPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long CANstressIsPending();
```

## Description

Serves to query whether the CANstress hardware is in the state **Pending**.

## Parameters

—

## Return Values

- **1**: If the CANstress hardware is in the state **Pending**.
- **0**: If the hardware is in another state (**Idle** or **Finished**).
- **-1**: On occurrence of an error.

## Example

—
