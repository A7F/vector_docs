[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Objects/CAPLfunctionEthernetErrorPacket.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetErrorPacket

# ethernetErrorPacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
ethernetErrorPacket <errorPacket var>;
```

## Description

Can be used in [on ethernetErrorPacket](../EventProcedures/CAPLfunctionOnEthernetErrorPacket.md) handler to access packet data.

## Parameters

- **packet var**: Character string defining the object’s variable name.

## Selectors

- **time_ns**: Point in time, units: nanoseconds  
  Type: `int64`  
  Access Limitation: Read only

- **dir**  
  Type: `byte`  
  Access Limitation: Read only

- **msgChannel**: Application channel, i.e. Eth 1.  
  Type: `word`  
  Access Limitation: —

- **hwChannel**: Hardware channel. If not supported by network interface, value is 1.  
  Type: `word`  
  Access Limitation: Only with Vector Interfaces, i.e. VN5640, with operation mode with more than 1 hardware channel. Channel-based network access only

- **hwPort**: Port used for network-based access.  
  Type: `ethernetPort`  
  Access Limitation: [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access only

- **Length**: Length of Ethernet payload data (starting after the Ethertype).  
  Type: `word`  
  Access Limitation: —

- **FCS**: Ethernet packet checksum. For some Ethernet hardware this value is not available (value 0).  
  Type: `word`  
  Access Limitation: Read only

- **FrameLen**: Frame duration in ns. For some Ethernet hardware this value is not available (value 0).  
  Type: `word`  
  Access Limitation: Read only

- **SOF**: Start-of-Frame time stamp in ns. For some Ethernet hardware this value is not available (value 0).  
  Type: `word`  
  Access Limitation: Read only

- **Type**: Ethertype  
  Type: `word`  
  Access Limitation: —

- **Source**: Source Ethernet MAC address. Only 6 bytes of the QWord are used and network byte order is used.  
  Type: `qword`  
  Access Limitation: —

- **Destination**: Destination Ethernet MAC address. Only 6 bytes of the QWord are used and network byte order is used.  
  Type: `qword`  
  Access Limitation: Read only

- **ErrorCode**: Channel-based mode in Rx direction (several error types can be set in one event):
  - 1: Invalid length of the Ethernet packet
  - 2: Invalid CRC of the Ethernet packet
  - 4: Invalid data received
  - 8: Collision detected (half duplex)

  Channel-based mode in Tx direction:
  - 1: No link
  - 2: Bypass enabled
  - 3: Phy error
  - 4: Overflow
  - 5: Wrong time
  - 6: Invalid CRC
  - 7: Invalid length
  - 8: No mirror

  [Network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) mode in Rx direction (several error types can be set in one event):
  - 1: Invalid length of the Ethernet packet
  - 2: Invalid CRC of the Ethernet packet
  - 4: Invalid data received
  - 8: Invalid **src** or **dest** MAC address

  [Network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) mode in Tx direction (several error types can be set in one event):
  - 0x01: No link
  - 0x02: PHY not yet configured
  - 0x04: PHY bypass activated
  - 0x08: RGMII converter in reset
  - 0x10: Invalid length
  - 0x20: Invalid CRC
  - 0x40: Invalid **src** or **dest** MAC address

  Type: `byte`  
  Access Limitation: Read only

## Example

```plaintext
on ethernetErrorPacket *
{
  write("Received Ethernet error packet on Eth%d", this.msgChannel );
  output( this ); // only required in CAPL node in measurement setup!
}
```

[See Also](javascript:void(0);)
