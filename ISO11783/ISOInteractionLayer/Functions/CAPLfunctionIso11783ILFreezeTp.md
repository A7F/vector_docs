[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILFreezeTp.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_FreezeTp**

# Iso11783IL_FreezeTp

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_FreezeTp(dword protocol, dword sa, dword da); //Form 1`
- `long Iso11783IL_FreezeTp(dbNode node, dword protocol, dword sa, dword da); //Form 2`

## Description

Function freezes the handling of the transport protocol connection by the current simulation node when the simulation node interacts as an originator or as a receiver in the connection, and the connection matches the given protocol (BAM RTS/CTS), source address and destination address. The source address specifies the originator (the node sending RTS or BAM) and the destination address specifies the receiver (the node sending CTS, or 255 for BAM) of a connection. If the connection was not found, an error will be returned.

Freezing a connection means, that the connection will be paused in the current state without reacting to any timeouts or messages.

Be aware that if you freeze a connection right after a message is sent, the response is not received at all, because the connection is already frozen when the responder sends its message. If you then unfreeze the connection again, the node waits for the response that it missed before and is not necessarily sending the next message.

To freeze a connection immediately you need to specify a delay for the transport protocol messages of 1 ms or greater, since the interaction layer will react on a message as soon as possible, and this may be before the CAPL function is handled. To setup delays for transport protocol messages, refer to the CAPL function [Iso11783IL_SetNodeProperty](CAPLfunctionIso11783ILSetNodeProperty.md).

**Note**: A node supports only one instance per destination address of each transport protocol at the same time. If the node holds a frozen connection, the connection must be killed before another can be established.

## Parameters

- **node**: Simulation node to apply the function.
- **protocol**:
  - 1: BAM
  - 2: RTS/CTS
  - 3: Fast Packet (not supported)
  - 4: ETP (ISO11783 Interaction Layer)
  - 5: FD TP BAM (not supported)
  - 6: FD TP RTS/CTS (not supported)
- **sa**: 0-255
- **da**: 0-255

## Return Values

- **0**: OK
- **0x050008**: Connection not found

## Example

```plaintext
variables
{
  const int kTpBam    = 1;
  const int kTpRtsCts = 2;
}

on start
{
  // Setup delays to allow immediate freeze
  Iso11783IL_SetNodeProperty("TPDTLatency", 2);
  Iso11783IL_SetNodeProperty("CTSLatency", 2);
  Iso11783IL_SetNodeProperty("EoMALatency", 2);
}

on key 'f'
{
  // Connection Node1 (originator) --> Nodes2 (receiver)
  Iso11783IL_FreezeTp(kTpRtsCts, 0x1, 0x2);
}

on key 'u'
{
  // Connection Node1 (originator) --> Nodes2 (receiver)
  Iso11783IL_UnfreezeTp(kTpRtsCts, 0x1, 0x2);
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)