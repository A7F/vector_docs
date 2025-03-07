[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetBTR.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressSetBTR

# CANstressSetBTR

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
void CANstressSetBTR (dword btr1, dword btr2);
```

## Description

Sets the value of the **B**us **T**iming **R**egister. This setting affects the baudrate of the CAN bus set in CANstress. The CAN controller data sheet will list valid pairs of values.

## Parameters

- **btr0**: New value for BTR0.
- **btr1**: New value for BTR1.

## Return Values

—

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)