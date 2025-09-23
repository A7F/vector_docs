# GPIBDevOnline

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long GPIBDevOnline (long deviceDescriptor, long mode);
```

## Description

Activates/deactivates the device.

## Parameters

- **deviceDescriptor**: Device ID
- **mode**:
  - 1: online
  - 0: offline

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—
