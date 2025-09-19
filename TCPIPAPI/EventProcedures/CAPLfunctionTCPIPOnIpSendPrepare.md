[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/EventProcedures/CAPLfunctionTCPIPOnIpSendPrepare.md)

**CAPL Functions** » **TCP/IP API** » **OnIpSendPrepare**

# OnIpSendPrepare

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long OnIpSendPrepare( dword socket, ethernetPacket * packet);
```

## Description

If the CAPL program implements this callback it is called right before a packet will be sent by the TCP/IP stack. It is possible to manipulate the content of the packet or to block the sending of the package on the bus.

**Note**: The callback is only available for simulation nodes using the individual TCP/IP stack instance. Check this setting in the [TCP/IP Stack](../../../CANoeCANalyzer/Ethernet/TCPIPNetworkSettings/PageStackSelection.md) configuration dialog.

## Parameters

- **socket**: The socket handle.
- **packet**: The [Ethernet packet](../../IP/Objects/CAPLfunctionEthernetPacket.md) which will be sent.

## Return Values

- **0**: Block the Ethernet packet.
- **1**: Send the Ethernet packet.

## Example

```plaintext
variables
{
  const dword INVALID_SOCKET = ~0;
  DWORD gUdpSocket;
}

on start
{
  dword result;
  char data[100] = "Hello world";
  // open udp socket
  gUdpSocket = UdpOpen(0, 0);
  if(gUdpSocket == INVALID_SOCKET)
  {
    writeLineEx(1,3,"%BASE_FILE_NAME%: Failed to open udp socket. Error: %d", IpGetLastError());
  }
  // send data on udp socket
  result = UdpSendTo(gUdpSocket, ipGetAddressAsNumber("192.168.1.1"), 21, data, strlen(data));
  if(result != 0)
  {
    writeLineEx(1,3,"%BASE_FILE_NAME%: Failed to send data on udp socket. Error: %d", IpGetLastSocketError(gUdpSocket));
  }
}

long OnIpSendPrepare( dword socket, ethernetPacket * packet)
{
  if(socket == gUdpSocket)
  {
    // change destination MAC id to broadcast
    packet.destination = ethGetMacAddressAsNumber("FF:FF:FF:FF:FF:FF");
    // change ip destination address to broadcast address.
    // Since this address is covered by the IP checksum this will
    // lead to a checksum error.
    packet.dword(16) = ipGetAddressAsNumber("255.255.255.255");
  }
  return 1; // send packet
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
