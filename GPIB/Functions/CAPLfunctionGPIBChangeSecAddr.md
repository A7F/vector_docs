[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/GPIB/Functions/CAPLfunctionGPIBChangeSecAddr.md)

**CAPL Functions** » **GPIB** » GPIBDevChangeSecAddr

# GPIBDevChangeSecAddr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long GPIBDevChangeSecAddr (long deviceDescriptor, long newAddr);
```

## Description

Changes the secondary address of a device.

## Parameters

- **deviceDescriptor**: Device ID
- **newAddr**: New secondary address

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: On error, if no GPIB driver is available

## Example

—
