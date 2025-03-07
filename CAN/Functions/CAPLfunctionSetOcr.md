[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionSetOcr.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » setOcr

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)