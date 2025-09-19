# canGetRxErrorCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetRxErrorCount(long channel);
```

## Description

Gets the total count of receive errors of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of receive errors, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
write("Receive errors on CAN1: %i", canGetRxErrorCount(1));
```
