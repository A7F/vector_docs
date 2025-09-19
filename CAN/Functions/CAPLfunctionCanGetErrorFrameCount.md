# canGetErrorFrameCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetErrorFrameCount(long channel);
```

## Description

Gets the total count of error frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of error frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Total count of error frames on CAN2: %i", canGetErrorFrameCount(2));
```
