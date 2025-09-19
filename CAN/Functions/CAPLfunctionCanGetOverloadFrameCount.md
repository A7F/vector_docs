# canGetOverloadFrameCount

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long canGetOverloadFrameCount(long channel);
```

## Description

Gets the total count of overload frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of overload frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Overload frame count of CAN1: %i", canGetOverloadFrameCount(1));
```
