# canGetExtRemoteCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long canGetExtRemoteCount(long channel);
```

## Description

Gets the total count of extended remote frames of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of extended remote frames, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Total count of extended remote frames on CAN1: %i", canGetExtRemoteCount(1));
```
