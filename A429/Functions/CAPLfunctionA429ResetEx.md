[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/A429/Functions/CAPLfunctionA429ResetEx.md)

[CAPL Functions](../../CAPLfunctions.md) » [A429](../CAPLfunctionsA429Overview.md) » a429ResetEx

# a429ResetEx

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long a429ResetEx( long channel );
```

## Description

Re-initialize the selected channel with the active channel parameters. The active channel parameters are read with [a429GetConfiguration](CAPLfunctionA429GetConfiguration.md) and modified with [a429SetConfiguration](CAPLfunctionA429SetConfiguration.md).

Note, that the channel is reset. The transmit queue and the hardware schedule table is emptied for this channel.

## Parameters

- **channel**: valid channel number

## Return Values

- **0**: could not re-initialize channel
- **1**: channel successfully re-initialized

## Example

```plaintext
on key 'r'
{
  if (a429ResetEx(RxChannel)) {
    write("reset channel '%d' OK", RxChannel);
  }
  else {
    write("reset channel '%d' failed", RxChannel);
  }

  if (a429ResetEx(TxChannel)) {
    write("reset channel '%d' OK", TxChannel);
  }
  else {
    write("reset channel '%d' failed", TxChannel);
  }
}
```

[See Also](javascript:void(0);)