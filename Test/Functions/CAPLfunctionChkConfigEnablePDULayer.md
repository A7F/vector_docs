# ChkConfig_EnablePDULayer

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkConfig_EnablePDULayer();
```

## Description

Enables the PDU layer for the current bus context. It affects the next checks that are created after calling this function.

Use this function to enable the PDU layer again after calling [ChkConfig_DisablePDULayer](CAPLfunctionChkConfigDisablePDULayer.md).

Default is enabled for a PDU network.

## Parameters

—

## Return Values

- **0**: Successful
- **-1**: Current bus context is not a PDU network.
- **-3**: Test Service Library was not initialized.

## Example

See [ChkConfig_DisablePDULayer](CAPLfunctionChkConfigDisablePDULayer.md)
