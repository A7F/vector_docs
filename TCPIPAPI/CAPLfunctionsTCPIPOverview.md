[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/CAPLfunctionsTCPIPOverview.md)

[CAPL Functions](../CAPLfunctions.md) » TCP/IP CAPL Functions

# TCP/IP CAPL Functions

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

The [TCP/IP API](../../Shared/CAPL/TCPIPAPI/TCPIPAPI.md) provides access to TCP/IP networking features. It is implemented on top of the native Winsock 2 API of the Windows operating system. The API falls into the following categories.

These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

**ON THIS PAGE:**

- [Further Topics](#BMFurtherTopics)
- [IP API](#IPAPI)
- [IPsec API](#IPsecAPI)
- [UDP API](#UDPAPI)
- [TCP API](#TCPAPI)

## IP API [▲ back](#Shortcuts)

The IP API consists of general functions for network information retrieval such as querying for installed network interface cards (NIC), IP addresses, address conversion functions, error handling, and so on. In addition, the IP API has some special functions for socket manipulations such as setting socket options or binding.

### Functions

- [IpAddAdapterAddress](Functions/CAPLfunctionIpAddAdapterAddress.md): Adds an address to the network interface with the given index.
- [IpBind](Functions/CAPLfunctionIPBind.md): Associates an address and a port with a specified socket.
- [IpGetAdapter](Functions/CAPLfunctionIPGetAdapter.md): Get the interface index of the given channel.
- [IpGetAdapterAddress](Functions/CAPLfunctionIPGetAdapterAddress.md): Retrieves the addresses associated with a network interface.
- [IpGetAdapterAddressAsString](Functions/CAPLfunctionIPGetAdapterAddressAsString.md): Retrieves the string representation of the first address associated with a specified network interface.
- [IpGetAdapterChannel](Functions/CAPLfunctionIPGetAdapterChannel.md): Get the channel number of the given adapter.
- [IpGetAdapterAddressCount](Functions/CAPLfunctionIpGetAdapterAddressCount.md): Gets the count of addresses assigned to an adapter.
- [IpGetAdapterCount](Functions/CAPLfunctionIPGetAdapterCount.md): Returns the number of network interfaces for the local computer.
- [IpGetAdapterDescription](Functions/CAPLfunctionIPGetAdapterDescription.md): Retrieves the description of a specified network interface.
- [IpGetAdapterGateway](Functions/CAPLfunctionIPGetAdapterGateway.md): Retrieves the default gateway address associated with a specified network interface.
- [IpGetAdapterGatewayAsString](Functions/CAPLfunctionIPGetAdapterGatewayAsString.md): Retrieves the string representation of the default gateway address associated with a specified network interface.
- [IpGetAdapterMacId](Functions/CAPLfunctionIpGetAdapterMacId.md): Gets the MAC id of an interface.
- [IpGetAdapterMask](Functions/CAPLfunctionIPGetAdapterMask.md): Retrieves the address masks associated with a specified network interface.
- [IpGetAdapterMaskAsString](Functions/CAPLfunctionIPGetAdapterMaskAsString.md): Retrieves the string representation of the first address mask associated with a specified network interface.
- [IpGetAdapterPrefix](Functions/CAPLfunctionIPGetAdapterPrefix.md): The function retrieves the address prefixes associated with the specified network interface.
- [IpGetAdapterVlanDefaultPriority](Functions/CAPLfunctionIPGetAdapterVlanDefaultPriority.md): Get the VLAN priority of the given adapter.
- [IpGetAdapterVlanId](Functions/CAPLfunctionIPGetAdapterVlanId.md): Get the VLAN id of the given adapter.
- [IpGetAddressAsArray](Functions/CAPLfunctionIPGetAddressAsArray.md): Converts an address string in colon notation to a 16 byte array with the address bytes in network order.
- [IpGetAddressAsNumber](Functions/CAPLfunctionIPGetAddressAsNumber.md): Converts an address string in dot notation to its [numerical value](../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md).
- [IpGetAddressAsString](Functions/CAPLfunctionIPGetAddressAsString.md): Converts a [numeric address](../../Shared/CAPL/TCPIPAPI/IPAddressByteOrdering.md) into an address string in dot notation.
- [IpGetHostByName](Functions/CAPLfunctionIpGetHostByName.md): Get the address for the given host name.
- [IpGetLastError](Functions/CAPLfunctionIPGetLastError.md): Returns the Winsock 2 error code of the last operation that failed.
- [IpGetLastSocketError](Functions/CAPLfunctionIPGetLastSocketError.md): Returns the Winsock 2 error code of the last operation that failed on a specified socket.
- [IpGetLastSocketErrorAsString](Functions/CAPLfunctionIPGetLastSocketErrorAsString.md): Retrieves the error message of the last operation that failed on a specified socket.
- [IpGetSocketAddressFamily](Functions/CAPLfunctionIpGetSocketAddressFamily.md): Gets the address family of a socket.
- [IpGetSocketName](Functions/CAPLfunctionIpGetSocketName.md): Gets the local address and port of a socket.
- [IpGetSocketOption](Functions/CAPLfunctionIpGetSocketOption.md): Reads the value of the given socket option.
- [IpGetStackParameter](Functions/CAPLfunctionIpGetStackParameter.md): Gets the value of the given parameter of the TCP/IP Stack.
- [IpJoinMulticastGroup](Functions/CAPLfunctionIPJoinMulticastGroup.md): Joins a multicast group on the given socket.
- [IpLeaveMulticastGroup](Functions/CAPLfunctionIPLeaveMulticastGroup.md): Leaves a previously joined multicast group.
- [IpRemoveAdapterAddress](Functions/CAPLfunctionIpRemoveAdapterAddress.md): Removes an address from the network interface with the given index.
- [IPRouteAddGateway](Functions/CAPLfunctionIPRouteAddGateway.md): Add a gateway route to the TCP/IP Stack.
- [IPRouteAddHost](Functions/CAPLfunctionIPRouteAddHost.md): Add a host route to the TCP/IP Stack.
- [IPRouteAddInterface](Functions/CAPLfunctionIPRouteAddInterface.md): Add an interface route to the TCP/IP Stack.
- [IPRouteDeleteGateway](Functions/CAPLfunctionIPRouteDeleteGateway.md): Delete a gateway route from the TCP/IP Stack.
- [IPRouteDeleteHost](Functions/CAPLfunctionIPRouteDeleteHost.md): Delete a host route from the TCP/IP Stack.
- [IPRouteDeleteInterface](Functions/CAPLfunctionIPRouteDeleteInterface.md): Delete an interface route from the TCP/IP Stack.
- [IpSetAdapterGateway](Functions/CAPLfunctionIpSetAdapterGateway.md): Sets the default gateway address.
- [IpSetAdapterMacId](Functions/CAPLfunctionIPSetAdapterMacId.md): Sets the MAC id of an interface.
- [IPSetAdapterStatus](Functions/CAPLfunctionIPSetAdapterStatus.md): Set a specific adapter of the TCP/IP stack up or down.
- [IpSetMulticastInterface](Functions/CAPLfunctionIPSetMulticastInterface.md): Set the interface for outgoing multicast messages.
- [IpSetSocketOption](Functions/CAPLfunctionIPSetSocketOption.md): Modifies a socket option.
- [IpSetStackParameter](Functions/CAPLfunctionIpSetStackParameter.md): Sets the value of the given parameter of the TCP/IP Stack.

### The IP API Supports the Following CAPL Callbacks:

- [OnIpAddressAdded](EventProcedures/CAPLfunctionTCPIPOnIpAddressAdded.md): It is called when an address gets added to a network interface.
- [OnIpAddressRemoved](EventProcedures/CAPLfunctionTCPIPOnIpAddressRemoved.md): It is called when an address gets removed from a network interface.
- [OnIpGetHostByName](EventProcedures/CAPLfunctionTCPIPOnIpGetHostByName.md): It is called when a blocking [IpGetHostByName](Functions/CAPLfunctionIpGetHostByName.md) function completes.
- [OnIpReceivePrepare](EventProcedures/CAPLfunctionTCPIPOnIpReceivePrepare.md): It is dispatched before a received packet will be dispatched to the TCP/IP stack.
- [OnIpSendPrepare](EventProcedures/CAPLfunctionTCPIPOnIpSendPrepare.md): It is called before a packet will be sent by the TCP/IP stack.

## IPsec API [▲ back](#Shortcuts)

### Functions

- [ipsecAssociationDatabaseAdd](Functions/CAPLfunctionIpsecAssociationDatabaseAdd.md): Adds a security association to the security association database.
- [ipsecAssociationDatabaseDelete](Functions/CAPLfunctionIpsecAssociationDatabaseDelete.md): Deletes a single spi from the security association database.
- [ipsecAssociationDatabaseDeleteAll](Functions/CAPLfunctionIpsecAssociationDatabaseDeleteAll.md): Deletes all dedicated spis from the security association database.
- [ipsecAssociationDatabaseFlush](Functions/CAPLfunctionIpsecAssociationDatabaseFlush.md): Flushes the security association database.
- [ipsecAssociationDatabaseGetSpi](Functions/CAPLfunctionIpsecAssociationDatabaseGetSpi.md): Creates a security association in the database.
- [ipsecAssociationDatabaseUpdate](Functions/CAPLfunctionIpsecAssociationDatabaseUpdate.md): Updates an existing security association in the database.
- [ipsecAssociationGetParameter](Functions/CAPLfunctionIpsecAssociationGetParameter.md): Gets a parameter value from the security association record.
- [ipsecAssociationInit](Functions/CAPLfunctionIpsecAssociationInit.md): Creates and initializes a security association record.
- [ipsecAssociationRelease](Functions/CAPLfunctionIpsecAssociationRelease.md): Releases the given security association record.
- [ipsecAssociationSetParameter](Functions/CAPLfunctionIpsecAssociationSetParameter.md): Sets a parameter in a security association record.
- [ipsecPolicyDatabaseAdd](Functions/CAPLfunctionIpsecPolicyDatabaseAdd.md): Adds a policy to the security policy database.
- [ipsecPolicyDatabaseDelete](Functions/CAPLfunctionIpsecPolicyDatabaseDelete.md): Deletes a single policy from the security policy database.
- [ipsecPolicyDatabaseFlush](Functions/CAPLfunctionIpsecPolicyDatabaseFlush.md): Deletes all policies in the security policy database.
- [ipsecPolicyGetParameter](Functions/CAPLfunctionIpsecPolicyGetParameter.md): Gets a parameter value from a security policy record.

### The IPsec API Supports the Following CAPL Callbacks:

- [OnIpsecSadbAcquire](EventProcedures/CAPLfunctionOnIpsecSadbAcquire.md): It is called when ipsec is acquired.

## UDP API [▲ back](#Shortcuts)

The UDP API is used for UDP communications. It provides a high-level interface for implementing connectionless, datagram-oriented communications.

### Functions

- [UdpClose](Functions/CAPLfunctionUDPClose.md): Closes the UDP socket.
- [UdpConnect](Functions/CAPLfunctionUDPConnect.md): Connects a UDP socket to the given remote address.
- [UdpOpen](Functions/CAPLfunctionUDPOpen.md): Creates a UDP socket for use in connectionless, datagram-oriented communications.
- [UdpReceiveFrom](Functions/CAPLfunctionUDPReceiveFrom.md): Receives data into a specified buffer.
- [UdpSend](Functions/CAPLfunctionUDPSend.md): Sends on a connected UDP socket.
- [UdpSendTo](Functions/CAPLfunctionUDPSendTo.md): Sends data to a specified location.

### The UDP API Supports the Following CAPL Callbacks:

- [OnUdpReceiveFrom](EventProcedures/CAPLfunctionTCPIPOnUdpReceiveFrom.md): It is called when an asynchronous receive operation on a UDP socket completes.
- [OnUdpSendTo](EventProcedures/CAPLfunctionTCPIPOnUdpSendTo.md): It is called when an asynchronous send operation on a UDP socket completes.

## TCP API [▲ back](#Shortcuts)

### Functions

- [TcpAbort](Functions/CAPLfunctionTCPAbort.md): Closes the TCP socket immediately and sends a RST. The socket is no longer valid.
- [TcpAccept](Functions/CAPLfunctionTCPAccept.md): Accepts an incoming connection request on a specified socket resulting in a new socket.
- [TcpClose](Functions/CAPLfunctionTCPClose.md): Closes the TCP socket.
- [TcpConnect](Functions/CAPLfunctionTCPConnect.md): Establishes a connection with a specified location.
- [TCPGetRemoteAddress](Functions/CAPLfunctionTCPGetRemoteAddress.md): Retrieves the remote address of the specified socket.
- [TCPGetRemoteAddressAsString](Functions/CAPLfunctionTCPGetRemoteAddressAsString.md): Retrieves the remote address of the specified socket in Internet standard dotted-decimal format.
- [TcpGetRemoteEndpoint](Functions/CAPLfunctionTCPGetRemoteEndpoint.md): Retrieves the remote endpoint of the specified connected socket.
- [TcpListen](Functions/CAPLfunctionTCPListen.md): Causes the socket to listen for incoming connection requests.
- [TcpOpen](Functions/CAPLfunctionTCPOpen.md): Creates a TCP socket for use in connection-based, message-oriented communications.
- [TcpReceive](Functions/CAPLfunctionTCPReceive.md): Receives data into a specified buffer.
- [TcpSend](Functions/CAPLfunctionTCPSend.md): Sends data on a specified socket.
- [TcpShutdown](Functions/CAPLfunctionTCPShutdown.md): Disables send operations on a specified socket.

### The TCP API Supports the Following CAPL Callbacks:

- [OnTcpClose](EventProcedures/CAPLfunctionTCPIPOnTcpClose.md): It is called when a TCP socket receives a close notification.
- [OnTcpConnect](EventProcedures/CAPLfunctionTCPIPOnTcpConnect.md): It is called when an asynchronous connection operation completes.
- [OnTcpListen](EventProcedures/CAPLfunctionTCPIPOnTcpListen.md): It is called when a connection request for a specified socket is received.
- [OnTcpReceive](EventProcedures/CAPLfunctionTCPIPOnTcpReceive.md): It is called when an asynchronous receive operation on a TCP socket completes.
- [OnTcpSend](EventProcedures/CAPLfunctionTCPIPOnTcpSend.md): It is called when an asynchronous send operation on a TCP socket completes.

[Winsock 2 Error Codes](CAPLfunctionsTCPIPWinsock2ErrorCodes.md) • [Technical Details](CAPLfunctionsTCPIPTechnicalDetails.md) • [Socket Options](CAPLfunctionsTCPIPSocketOptions.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)