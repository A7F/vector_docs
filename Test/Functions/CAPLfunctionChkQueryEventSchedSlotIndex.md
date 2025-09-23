# ChkQuery_EventSchedSlotIndex

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long ChkQuery_EventSchedSlotIndex (dword CheckId)
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
check.QueryEventSchedSlotIndex()
```

## Description

Retrieves slot index of a schedule table for which the event has been sent.

## Parameters

- **CheckId**: Identifier of the queried Check.

## Return Values

- **\< 0**: Refers the query [error codes](../CAPLfunctionsTSLErrorCodes.md)
- **≥ 0**: Refers to the slot index (0-indexed)

## Available For

- [ChkStart_LINSchedTableViolation](CAPLfunctionChkStartLinSchedTableViolation.md)
  - Result: Index of slot, where the violation took place

## Example

—
