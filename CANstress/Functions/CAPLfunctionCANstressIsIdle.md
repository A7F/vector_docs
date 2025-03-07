[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressIsIdle.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressIsIdle

# CANstressIsIdle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CANstressIsIdle();
```

## Description

Serves to query whether the CANstress hardware is in the state **Idle**.

## Parameters

—

## Return Values

- **1**: If the CANstress hardware is in the state **Idle**.
- **0**: If the hardware is in another state (**Pending** or **Finished**).
- **-1**: On occurrence of an error.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)