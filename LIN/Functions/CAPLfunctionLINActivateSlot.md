# linActivateSlot

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINActivateSlot.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linActivateSlot

**Valid for:** CANoe DE

## Function Syntax

```
long linActivateSlot(dword tableIndex, dword slotIndex);
```

## Description

Reactivates a schedule table slot defined in the LIN database file (LDF), after having been previously deactivated by [linDeactivateSlot()](CAPLfunctionLINDeactivateSlot.md).

Schedule slots containing MasterRequests are automatically sent only if their data is updated i.e. using output().

**Note:** If the Master node is not simulated or no schedule tables are defined, then this function will have no effect.

## Parameters

- **tableIndex**: Schedule table index according to the LIN database file (LDF). First table in the LDF has the index 0.
- **slotIndex**: Slot index. First slot in a table has the index 0.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

—

[linDeactivateSlots](CAPLfunctionLINDeactivateSlot.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)