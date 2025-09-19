# CANstressIsIdle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CANstressIsIdle();
```

## Description

Serves to query whether the CANstress hardware is in the state **Idle**.

## Parameters

—

## Return Values

- **1**: If the CANstress hardware is in the state **Idle**.
- **0**: If the hardware is in another state (**Pending** or **Finished**).
- **-1**: On occurrence of an error.

## Example

—
