[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressStart.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressStart

# CANstressStart

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
long CANstressStart();
```

## Description

Orders the CANstress COM server to activate the hardware for the error disturbance activity. If there is no connection between the CANstress software and the CANstress hardware, this is established previously.

## Parameters

—

## Return Values

- **0**: If successful.
- **-1**: In case of error (due to an internal error).
- **-2**: In case of error (due to an internal timeout).

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)