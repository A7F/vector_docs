# StandardFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long StandardFrameRate ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.StandardFrameRate
```

## Description

Returns the current rate of standard CAN messages on channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current rate of standard CAN frames on channel **x** in messages per second.

## Example

```
write ("Rate of standard frames on CAN1 = %d", CAN1.StandardFrameRate);
```
