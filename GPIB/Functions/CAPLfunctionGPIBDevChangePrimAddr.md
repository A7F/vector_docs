# GPIBDevChangePrimAddr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBDevChangePrimAddr (long deviceDescriptor, long newAddr);
```

## Description

Changes the primary address of a device.

## Parameters

- **deviceDescriptor**: Device ID
- **newAddr**: New primary address

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—
