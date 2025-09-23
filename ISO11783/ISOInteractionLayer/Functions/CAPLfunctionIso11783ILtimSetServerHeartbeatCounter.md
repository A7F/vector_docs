[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILtimSetServerHeartbeatCounter.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_TIMSetServerHeartbeatCounter**

# Iso11783IL_TIMSetServerHeartbeatCounter

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_TIMSetServerHeartbeatCounter(byte hearbeatCounter); // form 1
long Iso11783IL_TIMSetServerHeartbeatCounter(dbNode server, byte hearbeatCounter); // form 2
```

## Description

Sets the heartbeat counter of message **TIM_ServerStatus_Msg**. The next status message uses the new heartbeat counter value.

- If the new value is less than 251 (0xFB), then the counter is incremented as usual (after reaching the value 250 (0xFA) the counter restarts with value 0 again).
- If the new value is 251 (0xFB), then after a single transmission of the status message with the value 251 the counter is reset to value 0 and incremented as usual.
- If the new value of the counter is 252 or greater, then the status message is always sent with the same heartbeat counter value.

## Parameters

- **server**: TIM server simulation node to apply the function.
- **heartbeatCounter**: This heartbeat counter value is sent in the next status message, 0..255.

  Special values:

  - **251 (0xFB)**: Reset of Heartbeat counter
  - **252, 253 (0xFC, 0xFD)**: Reserved values
  - **254 (0xFE)**: Error condition on sender
  - **255 (0xFF)**: Graceful shutdown

## Return Values

- **0**: Function has been executed successfully
- **1**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

—
