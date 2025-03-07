[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthStartPacketGenerator.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethStartPacketGenerator

# ethStartPacketGenerator

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This feature is only available in real mode and with specific types of Vector Ethernet hardware. See **VN5000 Ethernet Interface Family Manual** for details.

## Function Syntax

```plaintext
long ethStartPacketGenerator( ethernetPacket txPacket, dword transmissionRate );
long ethStartPacketGenerator( ethernetPacket txPacket, dword transmissionRate, dword numberOfFrames );
long ethStartPacketGenerator( ethernetPacket txPacket, dword transmissionRate, dword numberOfFrames, dword counterByteOffset );
```

## Description

Starts the Ethernet packet generator that sends continuously the configured packets.

It is possible to run the packet generator for one packet per Ethernet channel or port. If you do not specify a number of Frames the generator sends until you call [EthStopPacketGenerator](CAPLfunctionEthStopPacketGenerator.md).

**Note**

- In network-based mode the sender port must be defined in the txPacket and reference a physical measurement port.
- The packet generator operates at the lowest priority; it will not send frames while other frames are in progress. This means that frame transmission will be delayed from the packet generator if another frame is being transmitted. At the end of the frame conflict, the packet generator may send 2 frames immediately after each other. The packet generator will not try to catch-up other missed frames.
- The generator is not supported for measurement ports that are connected to a multidrop segment in the hardware configuration.

## Parameters

- **txPacket**: The Ethernet packet to send.
- **transmissionRate**: The rate in frames per second the packet should be transmitted.
  - Range: [1 ... 1,000,000] in channel-based mode.
  - Range: [1 ... 30,000,000] in network-based mode.
- **numberOfFrames**: The number of Frames that should be transmitted overall. Range: [0x1 ... 0xFFFFFFFE], 0xFFFFFFFF to send until EthStopPacketGenerator.
- **counterByteOffset**: The position a 4 byte counter is placed inside the Ethernet-payload on a zero based index. Index 0 is the first byte after the source MAC Address. Take care that the counter has to fit completely into the payload.  
  E.g. for a packet with 100 byte Ethernet payload the highest position for a 4 byte counter is 96.

## Return Values

- **0**: Success
- **-1**: Output on specified Ethernet channel not allowed.
- **-2**: Packet generator not supported in simulation mode.
- **-3**: Packet generator is only available with Vector Ethernet network hardware.
- **-4**: Configuration of packet generator failed.
- **-5**: Starting of packet generator failed.

## Example

**Example for network-based access**

```plaintext
variables
{
  ethernetPacket txPacket;
}

on key '1'
{
  txPacket.hwPort = ethernetPort::Ethernet1::ChatClient1;
  txPacket.source = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
  txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
  txPacket.Length      = 100;
  txPacket.type        = 0xF123;
  ethStartPacketGenerator( txPacket, 1000 );
}

on key '2'
{
  ethStopPacketGenerator(txPacket);
}
```

**Example for channel-based access**

```plaintext
variables
{
  ethernetPacket txPacket;
}

on key '1'
{
  txPacket.msgChannel  = 1;
  txPacket.source      = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
  txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
  txPacket.Length      = 100;
  txPacket.type        = 0xF123;
  ethStartPacketGenerator( txPacket, 1000 );
}

on key '2'
{
  ethStopPacketGenerator(txPacket);
}
```

[See Also](javascript:void(0);)