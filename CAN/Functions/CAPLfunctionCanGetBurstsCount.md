# canGetBurstsCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canGetBurstsCount(long channel);
```

## Description

Gets the total count of bursts of a CAN channel.

## Parameters

- **channel**: CAN channel (1…32).

## Return Values

Total count of bursts, if CAN statistics is enabled; 0 otherwise.

## Example

```plaintext
long value;

value = canGetBurstsCount(1);
// Do something with the value, e.g.:
if (value > 100) {
  // Some action…
}
```
