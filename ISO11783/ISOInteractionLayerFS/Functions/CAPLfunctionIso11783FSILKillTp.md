[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILKillTp.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_KillTp**

# FSIL_KillTp

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_KillTp(dword protocol, dword sa, dword da); //Form 1
long FSIL_KillTp(dbNode node, dword protocol, dword sa, dword da); //Form 2
```

## Description

Kills (silently closes) the current transport protocol (BAM, RTS/CTS) connection that matches the given protocol, source address and destination address. The source address specifies the originator (the node sending RTS or BAM) and the destination address specifies the receiver (the node sending CTS, or 255 for BAM) of a connection. If the connection was not found, an error will be returned.

The connection and all its data will be deleted.

If a connection was only frozen, another connection will be accepted only if the frozen connection was killed.

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
  FSIL_SetNodeProperty("TPDTLatency", 2);
  FSIL_SetNodeProperty("CTSLatency", 2);
  FSIL_SetNodeProperty("EoMALatency", 2);
}

on key 'f'
{
  // Connection Node1 (originator) --> Nodes2 (receiver)
  FSIL_FreezeTp(kTpRtsCts, 0x1, 0x2);
}

on key 'u'
{
  // Connection Node1 (originator) --> Nodes2 (receiver)
  FSIL_KillTp(kTpRtsCts, 0x1, 0x2);
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
