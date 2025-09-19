# canDisturbanceTriggerDisable

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

```plaintext
long canDisturbanceTriggerDisable(long deviceID);
```

## Description

Disables the currently configured trigger on the CAN Disturbance Interface.

If no trigger is configured for the device, the function also returns success.

## Parameters

- **deviceID**: The unique device ID of the configured trigger.

## Return Values

- **1**: Segment is added to the sequence
- **0**: Segment is not added to the sequence
- **-1**: Device ID was not assigned to CAN Disturbance Interface

## Example

```plaintext
on key '1'
{
    long deviceID = @CANDisturbanceInterface1::DeviceNo;
    CanDisturbanceTriggerDisable (deviceID);
}
```

•  Technical References are only available in English
