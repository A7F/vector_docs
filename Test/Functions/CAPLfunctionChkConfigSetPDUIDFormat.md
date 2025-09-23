# ChkConfig_SetPDUIDFormat

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
long ChkConfig_SetPDUIDFormat(dword format);
```

## Description

Sets the format of the header ID for the current bus context. It affects the next checks that are created after calling this function.

It may be used if not the default header ID format shall be used. Default:

- Short header ID: CAN, FlexRay
- Long header ID: Ethernet

## Parameters

- **format**: Format of the header ID.
  - 0: Default
  - 1: Use always short header ID
  - 2: Use always long header ID

## Return Values

- **0**: Successful
- **-1**: Current bus context is not a PDU network.
- **-3**: Test Service Library was not initialized.

## Example

See [ChkConfig_DisablePDULayer](CAPLfunctionChkConfigDisablePDULayer.md)
