[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnIpReceivePrepare.md)

**CAPL Functions** » **TCP/IP API** » **OnIpReceivePrepare**

# OnIpReceivePrepare

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnIpReceivePrepare(ethernetPacket * packet);
```

## Description

If the CAPL program implements this callback, it is called right before a received packet will be dispatched to the TCP/IP stack. It is possible to manipulate the content of the packet or to block the receiving of the package from the bus.

**Note:** The callback is only available for simulation nodes using the individual TCP/IP stack instance. Check this setting in the CANoe DE product [TCP/IP Stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md) configuration dialog.

## Parameters

- **packet**: The received Ethernet packet.

## Return Values

- **0**: Block the Ethernet packet.
- **1**: Pass the Ethernet packet to the TCP/IP stack.

## Example

```plaintext
long OnIpReceivePrepare(ethernetPacket * packet)
{
  // block all packets with a broadcast destination MAC id
  if(packet.destination == 0xFFFFFFFFFFFFLL)
  {
    write("packet blocked");
    return 0;
  }
  write("packet passed to tcp/ip stack");
  return 1;
}
```
