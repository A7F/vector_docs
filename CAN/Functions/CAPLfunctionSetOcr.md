# setOcr

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```
setOcr(long channel, byte ocr);
```

## Description

Sets the Output Control Register. The values do not become active until the next call of the function [resetCan()](CAPLfunctionResetCan.md).

It should be noted that these values depend on the CAN platform used.

## Parameters

- **CAN channel**
  - **0**: all channels
  - **> 0**: only the given channel
- **OCR**: Value of the Output Control Register

## Return Values

- **1**: success
- **0**: error

## Example

```plaintext
...
setOcr(0, 0x02); // set
resetCan(); // activate
...
```

[resetCan](CAPLfunctionResetCan.md) • [setBtr](CAPLfunctionSetBtr.md)
