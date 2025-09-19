# canGetTransceiverErrorCount

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long canGetTransceiverErrorCount(long channel);
```

## Description

Gets the total count of transceiver errors of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of transceiver errors, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Transceiver errors on CAN1: %i", canGetTransceiverErrorCount(1));
```
