# canGetStdRemoteCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetStdRemoteCount(long channel);
```

## Description

Gets the total count of standard remote frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of standard remote frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Count of remote frames on CAN2: %i", canGetStdRemoteCount(2));
```
