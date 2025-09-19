# TxChipErrorCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long TxChipErrorCount ()
```

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
CANx.TxChipErrorCount
```

## Description

Returns the current number of Tx errors in the CAN receiver of channel **x**.

Valid **x** values: 1…32

## Parameters

—

## Return Values

Current number of errors in the CAN receiver of channel **x**.

## Example

```plaintext
write ("Number of Tx errors in receiver of CAN1 = %d", CAN1.TxChipErrorCount);
```
