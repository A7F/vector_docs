# canFlushTxQueue

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```
long canFlushTxQueue(long channel);
```

## Description

Flushes the Tx queue for the defined channel.

## Parameters

- **Channel**: The CAN channel.

## Return Values

- **0**: Interface doesn’t support flush of Tx queue
- **1**: success
- **-1**: error

## Example

```plaintext
on key 'f'
{
  int result;
  //flush Tx queue for CAN channel 1

  result = canFlushTxQueue(1);
  if(result == 1)
    write("Tx queue flushed ");
  else
    write("Tx queue flush failed Result =%d ", result);
}
```
