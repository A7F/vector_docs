[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressSetDisturbanceSequence.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressSetDisturbanceSequence

# CANstressSetDisturbanceSequence

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void CANstressSetDisturbanceSequence (char sequence[], dword resolution);
```

## Description

Sets the disturbance sequence.

## Parameters

- **sequence**: Describes the sequence as a string of **0**, **1**, **a**, and **u** characters, whereby **0** stands for dominant, **1** for recessive, **a** for an analog disturbance and **u** for undisturbed. A disturbance sequence can contain up to 2048 characters.
- **resolution**: Sets the resolution of the disturbance sequence. Possible values are **0** for bit times and **1** for BTL cycles.

## Return Values

—

## Example

```plaintext
CANstressSetDisturbanceSequence("uuuu1111", 0);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)