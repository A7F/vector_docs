[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressIsFinished.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressIsFinished

# CANstressIsFinished

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long CANstressIsFinished();
```

## Description

Serves to query whether the CANstress hardware is in the state **Finished**.

## Parameters

—

## Return Values

- **1**: If the CANstress hardware is in the state **Finished**.
- **0**: If the hardware is in another state (**Idle** or **Pending**).
- **-1**: On occurrence of an error.

## Example

—

•  Technical References are only available in English

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)