# RxChipErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long RxChipErrorCount ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.RxChipErrorCount
```

## Description

Returns the current Rx error count in the receiver of channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current error count in the receiver of channel **x**.

## Example

```plaintext
write ("Rx error count in the receiver of CAN1 = %d", CAN1.RxChipErrorCount);
```
