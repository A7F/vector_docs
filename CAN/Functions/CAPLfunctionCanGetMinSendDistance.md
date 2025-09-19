# canGetMinSendDistance

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetMinSendDistance(long channel);
```

## Description

Gets the minimum distance between two consecutive frames of a CAN channel in milliseconds.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Minimum distance between two consecutive frames in milliseconds, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Minimum send distance on CAN1: %i [ms]", canGetMinSendDistance(1));
```
