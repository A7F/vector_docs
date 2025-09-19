# canActivateTxSelfAck

**Valid for**: CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
int canActivateTxSelfAck (int channel, int activate);
```

## Description

Activates/deactivates the transmit [self ack feature](../../../CANoeCANalyzer/Ribbon/Hardware/NetworkHardware/NetworkHardwareCANControllerConfiguration.md) for the defined channel.

## Parameters

- **channel**: CAN channel
- **activate**:
  - 0 = deactivate
  - 1 = activate

## Return Values

- **0**: device does not support self ack
- **1**: successful
- **-1**: In case of error

## Example

```plaintext
on key a'
{
  int channel
  int activate;
  // Activate TX Self-ACK for CAN channel 1
  channel = 1;
  activate = 1;
  canActivateTXSelfAck(channel, activate);
}
```
