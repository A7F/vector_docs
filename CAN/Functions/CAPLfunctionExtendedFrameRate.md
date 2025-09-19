# ExtendedFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long ExtendedFrameRate ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.ExtendedFrameRate
```

## Description

Returns the current rate of extended CAN messages on channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current rate of extended CAN messages on channel **x** in messages per second.

## Example

```plaintext
write ("Rate of extended frames on CAN1 = %d", CAN1.ExtendedFrameRate);
```
