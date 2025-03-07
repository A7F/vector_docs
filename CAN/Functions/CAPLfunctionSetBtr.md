[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CAN/Functions/CAPLfunctionSetBtr.md)

[CAPL Functions](../../CAPLfunctions.md) » [CAN](../CAPLfunctionsCANOverview.md) » setBtr

# setBtr

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long setBtr(long channel, byte btr0, byte btr1);
```

## Description

Sets another baudrate. The values do not become active until the next call of the function [resetCan](CAPLfunctionResetCan.md).

It should be noted that these values depend on the CAN controller used.

## Parameters

- **CAN channel**  
  - **0**: All controllers
  - **1 - 32**: channel 1 - 32

- **BTR0**: Value of Bit Timing Register 0.

- **BTR1**: Value of Bit Timing Register 1.

## Return Values

Always 1

## Example

```plaintext
...
setBtr(0, 0x00, 0x3a); // 500 kBaud for 82C200
resetCan(); // activate
...
```

[resetCan](CAPLfunctionResetCan.md) • [setOcr](CAPLfunctionSetOcr.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)