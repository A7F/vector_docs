[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthStopPacketGenerator.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethStopPacketGenerator

# ethStopPacketGenerator

**Valid for**: CANoe DE • CANoe4SW DE

**Note**  
This feature is only available in real mode and with specific types of Vector Ethernet hardware. See **VN5000 Ethernet Interface Family Manual** for details.

## Function Syntax

```plaintext
long ethStopPacketGenerator( ethernetPacket txPacket );
```

## Description

Stops the Ethernet packet generator, which was started with [EthStartPacketGenerator](CAPLfunctionEthStartPacketGenerator.md).

## Parameters

- **txPacket**: The Ethernet packet which was used to start the generator.

## Return Values

- **0**: Success
- **-1**: Output on specified Ethernet channel not allowed.
- **-2**: Packet generator not supported in simulation mode.
- **-3**: Packet generator is only available with Vector Ethernet network hardware.
- **-5**: Stopping the packet generator failed.

## Example

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
  EthStartPacketGenerator( txPacket, 1000 );
}

on key '2'
{
  ethStopPacketGenerator(txPacket);
}
```

[See Also](javascript:void(0);)