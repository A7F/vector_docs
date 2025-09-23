# GPIBWriteStr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long GPIBWriteStr 
(long deviceDescriptor, char cmdStr[]);
```

## Description

Writes **cmdStr** to the device. The function returns immediately and does not wait for the end of the command transmission.

## Parameters

- **deviceDescriptor**: Device ID
- **cmdStr**: GPIB command

## Return Values

- [Status](../CAPLfunctionsGPIBStatus.md)
- **-1**: on error, if no GPIB driver is available

## Example

Setting of a voltage of 1.23 V: `GPIBWriteStr(myDev, "V 1.23")`
