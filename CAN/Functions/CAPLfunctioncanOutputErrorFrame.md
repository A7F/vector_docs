# canOutputErrorFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canOutputErrorFrame(errorFrame, long dominant, long recessive);
```

## Description

Outputs an Error Frame to the CAN bus. The number of dominant bits and the number of trailing recessive bits are given as arguments.

## Parameters

- **errorFrame**: Variable of type errorFrame.
- **dominant**: Number of dominant bits.
- **recessive**: Number of recessive bits.

## Return Values

- **1**: OK
- **0**: error, e.g. not supported by driver

## Example

```plaintext
canOutputErrorFrame(errorFrame, 12, 0); //output Error Frame with 12 dominant bits on CAN1
canOutputErrorFrame(CAN2.errorFrame, 6, 0); //output Error Frame with 6 dominant bits on CAN2
```
