[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxIsPacketValid.md)

**CAPL Functions** » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxIsPacketValid

# AfdxIsPacketValid

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxIsPacketValid( long packet );
```

## Description

This function checks if a received packet has a protocol error. Packets with a protocol error are marked with an error icon in the Trace Window.

## Parameters

- **packet**: Handle of the message that should be checked.

## Return Values

- **0**: Packet is valid.
- **1**: Packet has protocol errors.

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  AfdxRegisterReceiveCallback("OnAfdxPacket");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnAfdxPacket(long dir, long line, int64 time, long bag, long afdxFlags, long packet)
{
  if (AfdxIsPacketValid(handle) != 0)
  {
    write("Receive packet with protocol error");
  }
}
```

[See Also](javascript:void(0);)