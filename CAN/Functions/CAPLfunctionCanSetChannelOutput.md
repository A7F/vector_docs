# canSetChannelOutput

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

**Note**  
This function can only be used with Vector drivers. The `vcndrvms.DLL` must be at least Version 4.2.40.

## Function Syntax

`long canSetChannelOutput(long channel, long silent);`

## Description

Defines the response of the CAN controller to the bus traffic and sets the ACK bit.  
The CAN transmitter of the channel is switched off. So no Ack bit is generated, and messages can no longer be sent. It is still possible to receive messages.

## Parameters

- **channel**: CAN channel
- **silent**:
  - `0`: silent
  - `1`: normal

## Return Values

- **0**: ok
- **!=0**: error

## Example

```plaintext
on key 's'
{
    long channel = 2;
    long silent = 0;
    canSetChannelOutput(channel, silent);
    Write("silent set to %d", silent);
}
```

[canSetChannelAcc](CAPLfunctionCanSetChannelAcc.md) • [canSetChannelMode](CAPLfunctionCanSetChannelMode.md)
