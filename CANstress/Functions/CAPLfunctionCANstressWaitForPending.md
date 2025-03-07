[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressWaitForPending.md)

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressWaitForPending

# CANstressWaitForPending

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long CANstressWaitForPending( dword timeout);
```

## Description

Waits until the CANstress hardware is in the state **Pending**.

## Parameters

- **timeout**: Specifies a maximal time in milliseconds that is waited. At the latest after the expiration of this time, the function returns.

  **Note**: With timeout = 0 an infinite time is waited until the state **Pending** occurs. Thus the additional test procedure is blocked if the state **Pending** is not reached.

## Return Values

- **0**: If successful.
- **1**: On occurrence of an internal error.
- **-2**: On return of the function due to a timeout.

## Example

—

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)