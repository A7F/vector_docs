[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINDeactivateSlot.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linDeactivateSlot

# linDeactivateSlot

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long linDeactivateSlot(dword tableIndex, dword slotIndex);
```

## Description

This function deactivates the specified slot of schedule table. For example, it can be used to turn slots off in a diagnostic table.

By calling this function in the event procedure [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md), it is possible to configure the initial state of the schedule table.

**Note**: If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

## Parameters

- **tableIndex**: Index of the schedule table to be configured. Value range: 0..N-1, where N is the total number of defined schedule tables.
- **slotIndex**: Index of slot to be deactivated within the specified schedule table. Value range: 0..Y-1, where Y is the total number of slots in the specified schedule table.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linActivateSlot](CAPLfunctionLINActivateSlot.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
