[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/CAPLfunctionsIPOverview.md)

## Ethernet CAPL Functions

[CAPL Functions](../CAPLfunctions.md) » [Ethernet](CAPLEthernetStartPage.md) » Ethernet CAPL Functions

**Valid for:** CANoe DE • CANoe4SW DE

### Ethernet

- Only available with Option Ethernet.
- With Option Ethernet several APIs are provided for receiving and transmitting Ethernet packets.
- These CAPL functions are supported by Windows and Linux. The functionality under Linux has not been fully tested yet.

---

**ON THIS PAGE:**

- [Event Procedures](#EventProcedures)
- [General Functions](#GeneralFunctions)
- [Methods](#Methods)
- [Objects](#Objects)
- [Stress Generator](#StressGenerator)

### Event Procedures [▲ back](#Shortcuts)

- [on ethernetErrorPacket](EventProcedures/CAPLfunctionOnEthernetErrorPacket.md): Is called if an erroneous Ethernet packet is received.
- [on ethernetMacsecStatus](EventProcedures/CAPLfunctionOnethernetMacsecStatus.md): Is called when the Ethernet MACsec connection state of a physical port has changed.
- [on ethernetPacket](EventProcedures/CAPLfunctionOnEthernetPacket.md): Is called up after an Ethernet packet has been received.
- [on ethernetPacketForwarded](EventProcedures/CAPLfunctionOnEthernetPacketForwarded.md): Is called up after a the network interface has forwarded a received Ethernet packet.
- [on ethernetPhyState](EventProcedures/CAPLfunctionOnEthernetPhyState.md): Is called when the state of an ethernet PHY has changed or any relevant activity has been triggered.
- [on ethernetStatus](EventProcedures/CAPLfunctionOnEthernetStatus.md): Is called if the status of an Ethernet link is changed.
- [on serviceSignal](EventProcedures/CAPLfunctionOnServiceSignal.md): Is called if value of received Service Signal has changed.
- [on serviceSignal_update](EventProcedures/CAPLfunctionOnServiceSignalUpdate.md): Is called if Service Signal is received.

### General Functions [▲ back](#Shortcuts)

- [GetServiceSignal](Functions/CAPLfunctionSomeIpGetServiceSignal.md): Reads the value of a Service Signal.
- [GetServiceSignalData](Functions/CAPLfunctionSomeIpGetServiceSignalData.md): Reads the data of a Service Signal.
- [GetServiceSignalString](Functions/CAPLfunctionSomeIpGetServiceSignalString.md): Reads the string value of a Service Signal.
- [SetServiceSignal](Functions/CAPLfunctionSomeIpSetServiceSignal.md): Sets the value of a Service Signal.
- [SetServiceSignalData](Functions/CAPLfunctionSomeIpSetServiceSignalData.md): Sets the data of a Service Signal.
- [SetServiceSignalString](Functions/CAPLfunctionSomeIpSetServiceSignalString.md): Sets the string value of a Service Signal.
- [ethClearMacAddressTable](Functions/CAPLfunctionEthClearMacAddressTable.md): Clears MAC address table of network interface.
- [ethGetLinkStatus](Functions/CAPLfunctionEthGetLinkStatus.md): Returns the link status of the channel.
- [ethSetLinkStatus](Functions/CAPLfunctionEthSetLinkStatus.md): Configures the channel of the Vector hardware to establish or destablish a link.
- [ethGetPhyConnector](Functions/CAPLfunctionEthGetPhyConnector.md): Gets the PHY connector.
- [ethGetMacAddressAsNumber](Functions/CAPLfunctionEthGetMacAddressAsNumber.md): Converts a MAC address from string to a number.
- [ethGetMacAddressAsString](Functions/CAPLfunctionEthGetMacAddressAsString.md): Converts a MAC address to a string.
- [ethGetMacsecSecureEntity](Functions/CAPLfunctionEthGetMacsecSecureEntity.md): Returns the MACsec Secure Entity associated with the given measurement port.
- [ethGetPortAccessEntity](Functions/CAPLfunctionethGetPortAccessEntity.md): Returns the MACsec Port Access Entity associated with the given measurement port.
- [ethGetPhyMedium](Functions/CAPLfunctionEthGetPhyMedium.md): Gets the PHY medium.
- [ethGetPhyMode](Functions/CAPLfunctionEthGetPhyMode.md): Gets the PHY mode.
- [ethGetPhyState](Functions/CAPLfunctionEthGetPhyState.md): Gets the PHY state.
- [ethSetPhyState](Functions/CAPLfunctionEthSetPhyState.md): Sets the PHY state.
- [ethResetStatistics](Functions/CAPLfunctionEthResetStatistics.md): Rest the statistics values of Eth<channel> object
- [output](Functions/CAPLfunctionOutputEthernet.md): Outputs an Ethernet packet.
- [ethGetEthernetPort](Functions/CAPLfunctionethGetEthernetPort.md): Gets the Ethernet port for the current simulation node.
- [ethGetEthernetPortInfos](Functions/CAPLfunctionEthGetEthernetPortInfos.md): Retrieves port related information of all connected network-based Ethernet devices.
- [ethInjectPacket](Functions/CAPLfunctionEthInjectPacket.md): Transmits an Ethernet packet by a specific Ethernet port.
- [lookupEthernetPort](Functions/CAPLfunctionLookupEthernetPort.md): Gets the Ethernet port for a port qualification string.
- [ethDisableStatisticsOfAllNetworks](Functions/CAPLfunctionEthDisableStatisticsOfAllNetworks.md): Disables or enables the processing of the RT statistic values for all ports on all Ethernet networks.
- [ethDisableStatisticsOfNetwork](Functions/CAPLfunctionEthDisableStatisticsOfNetwork.md): Disables or enables the processing of the RT statistic values for all ports of the Ethernet network on which the passed port exists.
- [ethDisableStatisticsOfPort](Functions/CAPLfunctionEthDisableStatisticsOfPort.md): Disables or enables the processing of the RT statistic values for one port.
- [ethGetLinkSpeed](Functions/CAPLfunctionEthGetLinkSpeed.md): Returns the link speed of the specified port.
- [ethGetRxBitRate](Functions/CAPLfunctionEthGetRxBitRate.md): Returns the RX bitrate of the specified port.
- [ethGetRxBytesTotalCount](Functions/CAPLfunctionEthGetRxBytesTotalCount.md): Returns the number of received bytes of the specified port.
- [ethGetRxErrorPacketsTotalCount](Functions/CAPLfunctionEthGetRxErrorPacketsTotalCount.md): Returns the number of received error packets of the specified port.
- [ethGetRxPacketRate](Functions/CAPLfunctionEthGetRxPacketRate.md): Returns the RX packet rate of the specified port.
- [ethGetRxPacketsTotalCount](Functions/CAPLfunctionEthGetRxPacketsTotalCount.md): Returns the number of received packets of the specified port.
- [ethGetSQI](Functions/CAPLfunctionEthGetSQI.md): Returns the SQI (Signal Quality Indicator) of the specified port.
- [ethGetTxBitRate](Functions/CAPLfunctionEthGetTxBitRate.md): Returns the TX bitrate of the specified port.
- [ethGetTxBytesTotalCount](Functions/CAPLfunctionEthGetTxBytesTotalCount.md): Returns the number of transmitted bytes of the specified port.
- [ethGetTxErrorPacketsTotalCount](Functions/CAPLfunctionEthGetTxErrorPacketsTotalCount.md): Returns the number of transmitted error packets of the specified port.
- [ethGetTxPacketRate](Functions/CAPLfunctionEthGetTxPacketRate.md): Returns the TX packet rate of the specified port.
- [ethGetTxPacketsTotalCount](Functions/CAPLfunctionEthGetTxPacketsTotalCount.md): Returns the number of transmitted packets of the specified port.
- [ethResetStatisticsOfAllNetworks](Functions/CAPLfunctionEthResetStatisticsOfAllNetworks.md): Resets the RT statistic values of all ports of all Ethernet networks.
- [ethResetStatisticsOfNetwork](Functions/CAPLfunctionEthResetStatisticsOfNetwork.md): Resets the RT statistic values of all ports of the Ethernet network on which the passed port exists.
- [ethResetStatisticsOfPort](Functions/CAPLfunctionEthResetStatisticsOfPort.md): Resets the RT statistic values of the port.

### Methods [▲ back](#Shortcuts)

Information on the protocol and field designators can be found on the [protocol’s help page](../../CANoeCANalyzer/Ethernet/Protocols/Protocol.md).

- [ethernetPacket::Clear](Methods/CAPLfunctionClear.md): Clears data and reset length.
- [ethernetPacket::CompletePacket](Methods/CAPLfunctionCompletePacket.md): Calculates the checksum and length field for all protocols contained in the packet.
- [ethernetPacket::FaultInjectDisableLengthPadding](Methods/CAPLfunctionFaultInjectDisableLengthPadding.md): Sends Ethernet packet, which is smaller than minimal allowed length.
- [ethernetPacket::FaultInjectFCS](Methods/CAPLfunctionFaultInjectFCS.md): Sends Ethernet packet with invalid frame checksum.
- [ethernetPacket::GetData](Methods/CAPLfunctionGetData.md): Copies the data of an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md) to a byte array, char array, CAPL struct or system variable struct.
- [ethernetPacket::GetBitLength](Methods/CAPLfunctionGetBitLength.md): Returns the number of bits of the specified field as **dword**.
- [ethernetPacket::GetInt](Methods/CAPLfunctionGetInt.md): Returns the value of the specified field as **int**.
- [ethernetPacket::GetInt64](Methods/CAPLfunctionGetInt64.md): Returns the value of the specified field as **int64**.
- [ethernetPacket::IsAvailable](Methods/CAPLfunctionIsAvailable.md): Checks whether the protocol and the **protocol** field are present in the Ethernet packet.
- [ethernetPacket::GetDestinationIPAddress](Methods/CAPLfunctionGetDestinationIPAddress.md): Returns the destination IP address as IP_Address.
- [ethernetPacket::GetDestinationIPEndpoint](Methods/CAPLfunctionGetDestinationIPEndpoint.md): Returns the destination IP address and UDP/TCP port as IP_Endoint.
- [ethernetPacket::GetPDU](Methods/CAPLfunctionGetPDU.md): Retrieves the PDU with index **n** in this packet.
- [ethernetPacket::GetProtocolErrorText](Methods/CAPLfunctionGetProtocolErrorText.md): Copies an error text to the buffer for invalid Ethernet packets.
- [ethernetPacket::GetSourceIPAddress](Methods/CAPLfunctionGetSourceIPAddress.md): Returns the source IP address as IP_Address.
- [ethernetPacket::GetSourceEndpoint](Methods/CAPLfunctionGetSourceIPEndpoint.md): Returns the source IP address and UDP/TCP port as IP_Endoint.
- [ethernetPacket::GetVlan](Methods/CAPLfunctionGetVlan.md): Returns the VLAN tag, if the Ethernet packet contains a VLAN tag.
- [ethernetPacket::GetVlanId](Methods/CAPLfunctionGetVlanId.md): Returns the VLAN ID, if the Ethernet packet contains a VLAN tag.
- [ethernetPacket::GetVlanPriority](Methods/CAPLfunctionGetVlanPriority.md): Returns the VLAN priority, if the Ethernet packet contains a VLAN tag.
- [ethernetPacket::HasProtocolError](Methods/CAPLfunctionHasProtocolError.md): Checks protocol errors.
- [ethernetPacket::HasVlan](Methods/CAPLfunctionHasVlan.md): Returns number of VLAN tags.
- [ethernetPacket::PDUCount](Methods/CAPLfunctionPDUCount.md): Returns the number of all PDUs in this message.
- [ethernetPacket::PDUOffset](Methods/CAPLfunctionPDUOffset.md): Returns the byte offset of the start of the PDU.
- [ethernetPacket::protocol::field::GetData](Methods/CAPLfunctionProtocolFieldGetData.md): Gets data of a protocol field within an Ethernet packet.
- [ethernetPacket::protocol::field::IsAvailable](Methods/CAPLfunctionProtocolFieldIsAvailable.md): Returns if a protocol field is available in the Ethernet packet.
- [ethernetPacket::protocol::field::ParseAddress](Methods/CAPLfunctionProtocolFieldParseAddress.md): Sets the protocol field, which has type IPv4 or IPv6 address.
- [ethernetPacket::protocol::field::SetData](Methods/CAPLfunctionProtocolFieldSetData.md): Sets payload data of a protocol within an Ethernet packet.
- [ethernetPacket::protocol::GetData](Methods/CAPLfunctionProtocolGetData.md): Gets payload data of a protocol within an Ethernet packet.
- [ethernetPacket::protocol::Init](Methods/CAPLfunctionProtocolInit.md): Initializes the protocol within a ethernetPacket.
- [ethernetPacket::protocol::IsAvailable](Methods/CAPLfunctionProtocolIsAvailable.md): Returns 1, if the ethernetPacket contains the protocol.
- [ethernetPacket::protocol::optional-structure::Clear](Methods/CAPLfunctionProtocolOptionalStructureClear.md): Removes a protocol option from the Ethernet packet.
- [ethernetPacket::protocol::optional-structure::Init](Methods/CAPLfunctionProtocolOptionalStructureInit.md): Adds a protocol option for a specific protocol to the Ethernet packet.
- [ethernetPacket::protocol::ResizeData](Methods/CAPLfunctionProtocolResizeData.md): Resizes the payload of a protocol within a ethernetPacket.
- [ethernetPacket::protocol::SetData](Methods/CAPLfunctionProtocolSetData.md): Sets payload data of a protocol within an Ethernet packet.
- [ethernetPacket::RemoveVlan](Methods/CAPLfunctionRemoveVlan.md): Remove a VLAN tag from an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md).
- [ethernetPacket::SetData](Methods/CAPLfunctionSetData.md): Copies bytes from a char array, byte array, CAPL struct or system variable struct to the data of an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md).
- [ethernetPacket::SetDestinationIPAddress](Methods/CAPLfunctionSetDestinationIPAddress.md): Sets the destination IP address.
- [ethernetPacket::SetDestinationIPEndpoint](Methods/CAPLfunctionSetDestinationIPEndpoint.md): Sets the destination IP address an the UDP/TCP port.
- [ethernetPacket::SetSourceIPAddress](Methods/CAPLfunctionSetSourceIPAddress.md): Sets the source IP address.
- [ethernetPacket::SetSourceIPEndpoint](Methods/CAPLfunctionSetSourceIPEndpoint.md): Sets the source IP address an the UDP/TCP port.
- [ethernetPacket::SetTxEventGeneration](Methods/CAPLfunctionSetTxEventGeneration.md): Enables/Disables send acknowledgment
- [ethernetPacket::SetVlan](Methods/CAPLfunctionSetVlan.md): Sets the VLAN tag of an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md).
- [ethernetPacket::SetVlanId](Methods/CAPLfunctionSetVlanId.md): Sets the VLAN ID of an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md).
- [ethernetPacket::SetVlanPriority](Methods/CAPLfunctionSetVlanPriority.md): Sets the VLAN priority of an [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md).
- [ethernetPacket::source::ParseAddress](Methods/CAPLfunctionSourceParseAddress.md): Sets the source or destination MAC address.
- [IP_Address::IsIPv4Address](Methods/CAPLfunctionIsIPv4Address.md): Checks if the current address is an IPv4 address.
- [IP_Address::IsIPv6Address](Methods/CAPLfunctionIsIPv6Address.md): Checks if the current address is an IPv6 address
- [IP_Address::IsBroadcast](Methods/CAPLfunctionIsBroadcast.md): Checks if the current address is a broadcast address.
- [IP_Address::IsMulticast](Methods/CAPLfunctionIsMulticast.md): Checks if the current address is a multicast address.
- [IP_Address::GetAddressAsArray](Methods/CAPLfunctionGetAddressAsArray.md): Copies the current IP address to the byte.
- [IP_Address::MatchesAddress](Methods/CAPLfunctionMatchesAddress.md): Compares two addresses.
- [IP_Address::ParseAddressFromString](Methods/CAPLfunctionParseAddressFromString.md): Converts the character string to an IPv4 or IPv6 address and sets this address to the IP address value.
- [IP_Address::PrintAddressToString](Methods/CAPLfunctionPrintAddressToString.md): Converts the IP address to a character string.
- [IP_Address::SetAddressAsArray](Methods/CAPLfunctionSetAddressAsArray.md): Copies the byte array to the IP address value.
- [IP_Endpoint::IsTCP](Methods/CAPLfunctionIsTCP.md): Checks if the current transport protocol of this endpoint is TCP.
- [IP_Endpoint::IsUDP](Methods/CAPLfunctionIsUDP.md): Checks if the current transport protocol of this endpoint is UDP.
- [IP_Endpoint::IsUnknown](Methods/CAPLfunctionIsUnknown.md): Checks if the current transport protocol of this endpoint is unknown.
- [IP_Endpoint::MatchesEndpoint](Methods/CAPLfunctionMatchesEndpoint.md): Compares two endpoints.
- [IP_Endpoint::ParseEndpointFromString](Methods/CAPLfunctionParseEndpointFromString.md): Converts the character string to an endpoint.
- [IP_Endpoint::PrintEndpointToString](Methods/CAPLfunctionPrintEndpointToString.md): Converts the endpoint to a character string.
- [IP_Endpoint::SetToTCP](Methods/CAPLfunctionSetToTCP.md): Sets the transport protocol to TCP.
- [IP_Endpoint::SetToUDP](Methods/CAPLfunctionSetToUDP.md): Sets the transport protocol to UDP.
- [IP_Endpoint::SetTransportProtocolToUnknown](Methods/CAPLfunctionSetTransportProtocolToUnknown.md): Invalidates the transport protocol.

**MACsec Access**

The methods in this category allow to access a measurement port's MACsec secure entity, if MACsec is configured for the port.

**Note**: It is important to note that manipulating a secure entity with currently executing MACsec Key Agreement can interfere badly and lead to unexpected behavior. MKA should always be deactivated in `on prestart` when planning to configure the SecY using this API.

- [EthernetMacsecConfiguration::GetCAK](Methods/CAPLfunctionGetCAK.md): Copies the current connectivity association key (CAK) of the given MACsec configuration into the byte array given as parameter.
- [EthernetMacsecConfiguration::GetCipherSuites](Methods/CAPLfunctionGetCipherSuites.md): Copies the currently configured cipher suite priority list of the given MACsec configuration into the qword array given as parameter.
- [EthernetMacsecConfiguration::GetCKN](Methods/CAPLfunctionGetCKN.md): Copies the connectivity key name (CKN) of the given MACsec configuration into the byte array given as parameter.
- [EthernetMacsecConfiguration::SetCAK](Methods/CAPLfunctionSetCAK.md): Sets the connectivity association key (CAK) of the MACsec configuration from the given byte array.
- [EthernetMacsecConfiguration::SetCipherSuites](Methods/CAPLfunctionSetCipherSuites.md): Sets the cipher suite priority list of the MACsec configuration from the given qword array.
- [EthernetMacsecConfiguration::SetCKN](Methods/CAPLfunctionSetCKN.md): Sets the current connectivity key name (CKN) of the MACsec configuration from the given byte array..
- [EthernetMacsecSecureEntity::CreateRxSA](Methods/CAPLfunctionCreateRxSA.md): Creates a secure association for receiving.
- [EthernetMacsecSecureEntity::CreateRxSC](Methods/CAPLfunctionCreateRxSC.md): Creates a secure channel for receiving.
- [EthernetMacsecSecureEntity::CreateTxSA](Methods/CAPLfunctionCreateTxSA.md): Creates a secure association for transmitting.
- [EthernetMacsecSecureEntity::CreateTxSC](Methods/CAPLfunctionCreateTxSC.md): Creates a secure channel for transmitting.
- [EthernetMacsecSecureEntity::DeleteRxSA](Methods/CAPLfunctionDeleteRxSA.md): Deletes a secure association for receiving.
- [EthernetMacsecSecureEntity::DeleteRxSC](Methods/CAPLfunctionDeleteRxSC.md): Deletes a receive secure channel.
- [EthernetMacsecSecureEntity::DeleteTxSA](Methods/CAPLfunctionDeleteTxSA.md): Deletes a secure association for transmitting.
- [EthernetMacsecSecureEntity::DeleteTxSC](Methods/CAPLfunctionDeleteTxSC.md): Deletes a transmit secure channel.
- [EthernetMacsecSecureEntity::GetCapability](Methods/CAPLfunctionGetCapability.md): Returns the MACsec capability of the secure entity.
- [EthernetMacsecSecureEntity::GetConfidentialityOffset](Methods/CAPLfunctionGetConfidentialityOffset.md): Returns the currently agreed confidentiality offset.
- [EthernetMacsecSecureEntity::GetCurrentCipherSuite](Methods/CAPLfunctionGetCurrentCipherSuite.md): Returns the ID of the currently agreed MACsec cipher suite.
- [EthernetMacsecSecureEntity::GetDefaultRxSC](Methods/CAPLfunctionGetDefaultRxSC.md): Returns the default secure channel used for receiving.
- [EthernetMacsecSecureEntity::GetIncludeSCI](Methods/CAPLfunctionGetIncludeSCI.md): Returns preset for the SC flag in the tag control information (TCI).
- [EthernetMacsecSecureEntity::GetReplayProtection](Methods/CAPLfunctionGetReplayProtection.md): Returns the replay protection settings.
- [EthernetMacsecSecureEntity::GetRxSAK](Methods/CAPLfunctionGetRxSAK.md): Returns the current secure association key (SAK) of the receive SA specified by it's SCI and AN.
- [EthernetMacsecSecureEntity::GetRxSalt](Methods/CAPLfunctionGetRxSalt.md): Returns the current XPN salt value of the receive SA specified by it's SCI and AN.
- [EthernetMacsecSecureEntity::GetRxSCStats](Methods/CAPLfunctionGetRxSCStats.md): Returns the secure channel’s receive statistic variables.
- [EthernetMacsecSecureEntity::GetSecYStats](Methods/CAPLfunctionGetSecYStats.md): Returns the secure entity's global transmit and receive statistic variables, according to IEEE802.1AE-2018.
- [EthernetMacsecSecureEntity::GetTxSAEnabled](Methods/CAPLfunctionGetTxSAEnabled.md): Gets the enable state of the specified transmit secure association.
- [EthernetMacsecSecureEntity::GetTxSAK](Methods/CAPLfunctionGetTxSAK.md): Returns the current secure association key (SAK) of the transmit SA specified by it’s SCI and AN.
- [EthernetMacsecSecureEntity::GetTxSalt](Methods/CAPLfunctionGetTxSalt.md): Returns the current XPN salt value of the transmit SA specified by it’s SCI and AN.
- [EthernetMacsecSecureEntity::GetTxSCStats](Methods/CAPLfunctionGetTxSCStats.md): Returns the secure channel’s transmit statistic variables.
- [EthernetMacsecSecureEntity::GetUseES](Methods/CAPLfunctionGetUseES.md): Returns preset for the end station (ES) flag in the tag control information (TCI).
- [EthernetMacsecSecureEntity::GetValidateFrames](Methods/CAPLfunctionGetValidateFrames.md): Returns the ValidateFrames setting.
- [EthernetMacsecSecureEntity::InitMacsec](Methods/CAPLfunctionInitMacsec.md): Initializes the secure entity.
- [EthernetMacsecSecureEntity::InstallKey](Methods/CAPLfunctionInstallKey.md): Installs a key under the specified key id, and with the specified key data.
- [EthernetMacsecSecureEntity::RegisterOnBeforeSendMKPDU](Methods/CAPLfunctionRegisterOnBeforeSendMKPDU.md): Register a callback function which is called each time before the MKA key server sends a MKPDU (EAPOL-MKA frame).
- [EthernetMacsecSecureEntity::RegisterOnBeforeSendMPDU](Methods/CAPLfunctionRegisterOnBeforeSendMPDU.md): Register a callback function which is called each time before a readily encoded MACsec frame (MPDU) is going to be transmitted.
- [EthernetMacsecSecureEntity::SetRxSAEnabled](Methods/CAPLfunctionSetRxSAEnabled.md): Enables or disables use of an existing secure association for receiving.
- [EthernetMacsecSecureEntity::SetTxSAEnabled](Methods/CAPLfunctionSetTxSAEnabled.md): Enables or disables use of an existing secure association for transmission.
- [EthernetMacsecSecureEntity::UpdateMkaICV](Methods/CAPLfunctionUpdateMkaICV.md): Recalculates the integrity check value (ICV) of a MKPDU.
- [EthernetMacsecSecureEntity::UpdateSecY](Methods/CAPLfunctionUpdateSecY.md): Configures the basic parameters of the secure entity.

### Objects [▲ back](#Shortcuts)

- [Eth](Objects/CAPLfunctionEth.md): Access to Ethernet link status and statistics.
- [ethernetErrorPacket](Objects/CAPLfunctionEthernetErrorPacket.md): Access information in [on ethernetErrorPacket](EventProcedures/CAPLfunctionOnEthernetErrorPacket.md).
- [EthernetMacsecSecureEntity](Objects/CAPLfunctionEthernetMacsecSecureEntity.md): Defines a variable of type EthernetMacsecSecureEntity.
- [EthernetMacsecConfiguration](Objects/CAPLfunctionEthernetMacsecConfiguration.md): Define a variable of type EthernetMacsecConfiguration.
- [EthernetPortAccessEntity](Objects/CAPLfunctionEthernetPortAccessEntity.md): Defines a variable of type EthernetPortAccessEntity.
- [ethernetPacket](Objects/CAPLfunctionEthernetPacket.md): Creates an Ethernet packet object.
- [IP_Address](Objects/CAPLfunctionIPAdredress.md): Variable type for IPv4 and IPv6 address.
- [IP_Endpoint](Objects/CAPLfunctionIPEndpoint.md): Variable type for IP endpoints.

### Stress Generator [▲ back](#Shortcuts)

Functions for Ethernet Stress Generator are only available with Vector Ethernet network interfaces.

- [ethStartPacketGenerator](Functions/CAPLfunctionEthStartPacketGenerator.md): Starts Ethernet Stress Generator.
- [ethStopPacketGenerator](Functions/CAPLfunctionEthStopPacketGenerator.md): Stops Ethernet Stress Generator.

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)