[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINStartScheduler.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linStartScheduler

# linStartScheduler

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
void linStartScheduler();
```

## Description

This function starts the internal scheduler, which begins a cyclical traversal of a last configured schedule table.

If this is the first time the scheduler started the first found schedule table, i.e. the schedule table with index 0, is used.

Calling this function before the measurement start is not necessary, since the scheduler is started automatically.

## Parameters

—

## Return Values

—

## Example

—

[linStopScheduler](CAPLfunctionLINStopScheduler.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)