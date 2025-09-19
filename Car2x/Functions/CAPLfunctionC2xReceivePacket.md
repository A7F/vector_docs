# C2xReceivePacket

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xReceivePacket.md)

**CAPL Functions** » **Car2x** » **C2xReceivePacket**

## Function Syntax

```plaintext
long C2xReceivePacket( char *onPacketCallback );
```

## Description

Use this function to register a [CAPL callback](../Callbacks/CAPLfunctionC2xOnC2xPacket.md) to receive WLAN packets. The callback has a packet handle as parameter and the functions to access the tokens can be used. The C2xGetThis-functions can be used to access the payload of the highest interpretable protocol.

The callback must have the following signature:

```plaintext
void <OnC2xPacket> ( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
```

## Parameters

- **onPacketCallback**: Name of [CAPL callback](../Callbacks/CAPLfunctionC2xOnC2xPacket.md)

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

**Node System - PreStart in CAPL Browser**

```plaintext
on preStart
{
  C2xReceivePacket("OnC2xPacket");
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  byte rx_data[1500];
  byte rx_packet[1500];
  long rx_length;
  long rx_headerLength;

  rx_headerLength = C2xGetTokenData(packet, "wlan", "header", elCount(rx_packet), rx_packet);
  // without Ethernet header
  rx_length = C2xGetTokenData(packet, "eth", "data", elCount(rx_data), rx_data);
  write ("rx_headerLength: %d", rx_headerLength);
  write ("rx_dataLength: %d", rx_length);
  memcpy_off(rx_packet, rx_headerLength, rx_data, 0, rx_length);
  rx_length += rx_headerLength;
  // Always use rx_length to access rx_packet!
  write ("rx_length: %d", rx_length);
}
```

