[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressIsPending.md)

**CAPL Functions** » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressIsPending

# CANstressIsPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long CANstressIsPending();
```

## Description

Serves to query whether the CANstress hardware is in the state **Pending**.

## Parameters

—

## Return Values

- **1**: If the CANstress hardware is in the state **Pending**.
- **0**: If the hardware is in another state (**Idle** or **Finished**).
- **-1**: On occurrence of an error.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)