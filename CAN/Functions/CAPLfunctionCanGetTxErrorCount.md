# canGetTxErrorCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetTxErrorCount(long channel);
```

## Description

Gets the total count of transmit errors of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of transmit errors, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Transmit errors on CAN1: %i", canGetTxErrorCount(1));
```
