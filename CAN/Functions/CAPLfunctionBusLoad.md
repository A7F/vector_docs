# BusLoad

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long BusLoad ()
```

## Method Syntax

[Method Syntax](../../../Shared/CAPL/General/ClassesAndObjects.md)

```
CANx.BusLoad
```

## Description

Returns the current busload of channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current busload of channel **x** in percent.

## Example

```plaintext
write ("CAN1 busload = %d", CAN1.BusLoad);
```
