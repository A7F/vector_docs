# canGetStdDataCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetStdDataCount(long channel);
```

## Description

Gets the total count of standard data frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of standard data frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Count of data frames on CAN2: %i", canGetStdDataCount(2));
```
