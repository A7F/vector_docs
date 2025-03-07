[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBDevGotoLocal.md)

**CAPL Functions** » **GPIB** » **GPIBDevGotoLocal**

# GPIBDevGotoLocal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBDevGotoLocal (long deviceDescriptor);
```

## Description

Sets a device into local mode. A successor GPIB command sets the device back into remote mode.

## Parameters

- **deviceDescriptor**: Device ID

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—