[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetPacket.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket

# ethernetPacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
ethernetPacket <packet var>;
```

## Method Syntax

- [ethernetPacket::Clear](../Methods/CAPLfunctionClear.md)
- [ethernetPacket::CompletePacket](../Methods/CAPLfunctionCompletePacket.md)
- [ethernetPacket::FaultInjectDisableLengthPadding](../Methods/CAPLfunctionFaultInjectDisableLengthPadding.md)
- [ethernetPacket::FaultInjectFCS](../Methods/CAPLfunctionFaultInjectFCS.md)
- [ethernetPacket::GetData](../Methods/CAPLfunctionGetData.md)
- [ethernetPacket::GetDestinationIPAddress](../Methods/CAPLfunctionGetDestinationIPAddress.md)
- [ethernetPacket::GetDestinationIPEndpoint](../Methods/CAPLfunctionGetDestinationIPEndpoint.md)
- [ethernetPacket::GetPDU](../Methods/CAPLfunctionGetPDU.md)
- [ethernetPacket::GetProtocolErrorText](../Methods/CAPLfunctionGetProtocolErrorText.md)
- [ethernetPacket::GetSourceIPAddress](../Methods/CAPLfunctionGetSourceIPAddress.md)
- [ethernetPacket::GetSourceEndpoint](../Methods/CAPLfunctionGetSourceIPEndpoint.md)
- [ethernetPacket::GetVlan](../Methods/CAPLfunctionGetVlan.md)
- [ethernetPacket::GetVlanId](../Methods/CAPLfunctionGetVlanId.md)
- [ethernetPacket::GetVlanPriority](../Methods/CAPLfunctionGetVlanPriority.md)
- [ethernetPacket::HasProtocolError](../Methods/CAPLfunctionHasProtocolError.md)
- [ethernetPacket::HasVlan](../Methods/CAPLfunctionHasVlan.md)
- [ethernetPacket::PDUCount](../Methods/CAPLfunctionPDUCount.md)
- [ethernetPacket::PDUOffset](../Methods/CAPLfunctionPDUOffset.md)
- [ethernetPacket::protocol::field::GetData](../Methods/CAPLfunctionProtocolFieldGetData.md)
- [ethernetPacket::protocol::field::IsAvailable](../Methods/CAPLfunctionProtocolFieldIsAvailable.md)
- [ethernetPacket::protocol::field::ParseAddress](../Methods/CAPLfunctionProtocolFieldParseAddress.md)
- [ethernetPacket::protocol::field::SetData](../Methods/CAPLfunctionProtocolFieldSetData.md)
- [ethernetPacket::protocol::GetData](../Methods/CAPLfunctionProtocolGetData.md)
- [ethernetPacket::protocol::Init](../Methods/CAPLfunctionProtocolInit.md)
- [ethernetPacket::protocol::IsAvailable](../Methods/CAPLfunctionProtocolIsAvailable.md)
- [ethernetPacket::protocol::optional-structure::Clear](../Methods/CAPLfunctionProtocolOptionalStructureClear.md)
- [ethernetPacket::protocol::optional-structure::Init](../Methods/CAPLfunctionProtocolOptionalStructureInit.md)
- [ethernetPacket::protocol::ResizeData](../Methods/CAPLfunctionProtocolResizeData.md)
- [ethernetPacket::protocol::SetData](../Methods/CAPLfunctionProtocolSetData.md)
- [ethernetPacket::RemoveVlan](../Methods/CAPLfunctionRemoveVlan.md)
- [ethernetPacket::SetData](../Methods/CAPLfunctionSetData.md)
- [ethernetPacket::SetDestinationIPAddress](../Methods/CAPLfunctionSetDestinationIPAddress.md)
- [ethernetPacket::SetDestinationIPEndpoint](../Methods/CAPLfunctionSetDestinationIPEndpoint.md)
- [ethernetPacket::SetSourceIPAddress](../Methods/CAPLfunctionSetSourceIPAddress.md)
- [ethernetPacket::SetSourceIPEndpoint](../Methods/CAPLfunctionSetSourceIPEndpoint.md)
- [ethernetPacket::SetVlan](../Methods/CAPLfunctionSetVlan.md)
- [ethernetPacket::SetVlanId](../Methods/CAPLfunctionSetVlanId.md)
- [ethernetPacket::SetVlanPriority](../Methods/CAPLfunctionSetVlanPriority.md)

## Description

Can be used to create an Ethernet send object. The object data can be manipulated by selectors associated with this object.

## Parameters

- **packet var**: Character string defining the object’s variable name.

## Selectors

- **time_ns**: Point in time, units: nanoseconds  
  Type: int64  
  Access Limitation: read-only

- **dir**: Direction of transmission, event classification; possible values: Rx, Tx  
  Type: byte  
  Access Limitation: —

- **msgChannel**: Application channel, i.e. Eth 1  
  Type: word  
  Access Limitation: —

- **hwChannel**: Hardware channel. If not supported by network interface, value is 1.  
  Type: word  
  Access Limitation: Only with Vector Interfaces, i.e. VN5640, with operation mode with more than 1 hardware channel. Channel-based network access only

- **hwPort**: Port used for network-based access. Setting the port automatically sets the **msgChannel** as the channel the port is assigned to.  
  Type: ethernetPort  
  Access Limitation: [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access only

- **Length**: Length of Ethernet payload data (starting after the Ethertype).  
  Type: word  
  Access Limitation: —

- **FCS**: Ethernet packet checksum. For some Ethernet hardware this value is not available (value 0).  
  Type: dword  
  Access Limitation: read-only

- **FrameLen**: Frame duration in ns. For some Ethernet hardware this value is not available (value 0).  
  Type: int64  
  Access Limitation: read-only

- **SOF**: Start-of-Frame time stamp in ns. For some Ethernet hardware this value is not available (value 0).  
  Type: int64  
  Access Limitation: read-only

- **Type**: Ethertype  
  Type: word  
  Access Limitation: —

- **Source**: Source Ethernet MAC address. Only 6 bytes of the QWord are used and network byte order is used.  
  Type: qword  
  Access Limitation: —

- **Destination**: Destination Ethernet MAC address. Only 6 bytes of the QWord are used and network byte order is used.  
  Type: qword  
  Access Limitation: —

- **byte(x)**: Message data byte (unsigned 8 bit); Offset 0 is the byte directly after the Ethertype.  
  Type: byte  
  Access Limitation: —

- **char(x)**: Message data byte (signed 8 bit); Offset 0 is the byte directly after the Ethertype.  
  Type: char  
  Access Limitation: —

- **word(x)**: Message data word (unsigned 16 bit); Offset 0 is the word directly after the Ethertype.  
  Type: word  
  Access Limitation: —

- **int(x)**: Message data word (signed 16 bit); Offset 0 is the int directly after the Ethertype.  
  Type: int  
  Access Limitation: —

- **dword(x)**: Message data word (unsigned 32 bit); Offset 0 is the dword directly after the Ethertype.  
  Type: dword  
  Access Limitation: —

- **long(x)**: Message data word (signed 32 bit); Offset 0 is the long directly after the Ethertype.  
  Type: long  
  Access Limitation: —

- **qword(x)**: Message data word (unsigned 64 bit); Offset 0 is the qword directly after the Ethertype.  
  Type: qword  
  Access Limitation: —

- **int64(x)**: Message data word (signed 64 bit); Offset 0 is the int64 directly after the Ethertype.  
  Type: int64  
  Access Limitation: —

- **Simulated**: Message has been sent by a simulated CAPL node; possible values: 0 (no), 1 (yes)  
  Type: byte  
  Access Limitation: read-only

- **`<protocol>`.byte/word/dword/qword/char/int/int64/long**  
  Type: byte, word, dword, qword, char, int, int64, long  
  Access Limitation: —

- **`<protocol>`.byteLength**  
  Type: long  
  Access Limitation: read-only

- **`<protocol>`.byteOffset**  
  Type: long  
  Access Limitation: read-only

- **`<protocol>`.`<field>`**  
  Type: byte, word, dword, qword (depends on field)  
  Access Limitation: —

- **`<protocol>.<field>.bitLength`**  
  Type: long  
  Access Limitation: read-only

- **<protocol>.<field>.bitOffset**  
  Type: long  
  Access Limitation: read-only

- **<protocol>.<field>.byteLength**  
  Type: long  
  Access Limitation: read-only

- **<protocol>.<field>.byteOffset**  
  Type: long  
  Access Limitation: read-only

- **<protocol>.<optional-structure>.<field>**  
  Type: byte, word, dword, qword (depends on field)  
  Access Limitation: —

## Example

### Example

```plaintext
ethernetPacket txPacket;
int i;

txPacket.msgChannel = 1;
txPacket.source      = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
txPacket.Length      = 100;
txPacket.type        = 0xF123;

for( i = 0; i < txPacket.Length; i++ )
{
  txPacket.Byte(i) = i & 0xFF;
}

output( txPacket );
```

### Example for network-based access

With Vector network interfaces in [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access, it is possible to send a packet directly to a specific port. If the **hwPort** selector is not initialized, the port of CAPL program simulation node is used. In this example, we send a packet directly to the **ChatClient1** port in the **Ethernet1** network.

```plaintext
ethernetPacket txPacket;
int i;

txPacket.hwPort = ethernetPort::Ethernet1::ChatClient1;
txPacket.source      = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
txPacket.Length      = 100;
txPacket.type        = 0xF123;

for( i = 0; i < txPacket.Length; i++ )
{
  txPacket.Byte(i) = i & 0xFF;
}

output( txPacket );
```

### Example for channel-based access

With Vector network interfaces in channel-based network access and in operation modes which supports more than 1 hardware channel, the selector **hwChannel** can be set to output on a specific hardware channel. If the **hwChannel** is not set or 0, the transfer function decides on which hardware channel(s) the packet is sent.

```plaintext
ethernetPacket txPacket;
int i;

txPacket.msgChannel  = 1;
txPacket.hwChannel   = 2;
txPacket.source      = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
txPacket.Length      = 100;
txPacket.type        = 0xF123;

for( i = 0; i < txPacket.Length; i++ )
{
  txPacket.Byte(i) = i & 0xFF;
}
output( txPacket );
```

[See Also](javascript:void(0);)