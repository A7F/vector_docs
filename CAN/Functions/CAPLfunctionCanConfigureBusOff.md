# canConfigureBusOff

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE

## Function Syntax

```plaintext
long canConfigureBusOff(long channel, long canId, long flags);
```

## Description

Uses the defined ID of a message to set the bus state to **BusOff**.

**Note:** This function requires minimum a Vector driver 9.6 and a network interface with ISO CAN FD support.

## Parameters

- **Channel**: The CAN channel.
- **canId**: Message ID that is used to set the bus state to **BusOff**.
  - **Note:** If the value -1 is used for this parameter, all IDs are used to reach the bus state **Bus Off**.
- **flags**:
  - 0 = Switches off the disturbance
  - 1 = Switches on the disturbance

## Return Values

- **1**: The disturbance for the defined ID was switched on successfully.
- **0**: The disturbance for the defined ID could not be switched on.

## Example

```plaintext
variables
{
  message 0x1 msg;  // define CAN message
}

on key '1'
{
  canConfigureBusOff(msg.msgChannel, msg.Id, 1); // enable disturbance
}
on key '2'
{
  output(msg);
}
on key '3'
{
  canConfigureBusOff(msg.msgChannel, msg.Id, 0); // disable disturbance
}
on key 'r'
{
  resetCanEx(1);
}
```
