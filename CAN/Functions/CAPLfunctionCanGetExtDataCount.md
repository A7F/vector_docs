# canGetExtDataCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetExtDataCount(long channel);
```

## Description

Gets the total count of extended data frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of extended data frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Total count of extended data frames on CAN1: %i", canGetExtDataCount(1));
```
