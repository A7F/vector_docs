# ExtendedRemoteFrameRate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long ExtendedRemoteFrameRate ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.ExtendedRemoteFrameRate
```

## Description

Returns the current rate of extended remote CAN messages on channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current rate of extended remote CAN messages on channel **x** in frames per second.

## Example

```
write ("Rate of extended remote messages on CAN1 = %d", CAN1.ExtendedRemoteFrameRate);
```
