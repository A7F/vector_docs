[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSvtsSetBackplaneRelay.md)

[CAPL Functions](../../CAPLfunctions.md) » [VT System](../CAPLfunctionsVTSystemOverview.md) » vtsSetBackplaneRelay

# vtsSetBackplaneRelay

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```
DWORD vtsSetBackplaneRelay(DWORD bpIndex, DWORD closed);
```

## Description

This function is only available on VT8006A/VT8012A or newer. First generation VT8006/VT8012 backplanes do not support this functionality.

## Parameters

- **bpIndex**: zero based index of the backplane to switch the relay on.
- **closed**: 0 opens the relay, 1 closes the relay

## Return Values

- **0**: Successful call
- **-1**: Non-specific error
- **-2**: **bpIndex** is invalid
- **-3**: **closed** is invalid
- **-6**: The backplane does not support this functionality

## Example

```c
// Close the relay on the first backplane
vtsSetBackplaneRelay(0, 1);
```
