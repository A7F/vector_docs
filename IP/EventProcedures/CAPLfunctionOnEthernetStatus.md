[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/EventProcedures/CAPLfunctionOnEthernetStatus.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **on ethernetStatus**

# on ethernetStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `on ethernetStatus *;` // form 1
- `on ethernetStatus msgChannel<X>.*;` // form 2
- `on ethernetStatus ethernetPort::<Network>::<PortName>;` // form 3

## Description

The event procedure is called on the change of the status of the Ethernet link.

To access the control information you would use **selectors**.

The key word [this](../../Other/EventProcedures/CAPLfunctionKeywordThis.md) is available within an **on ethernetStatus** procedure, to access the information of the link status.

## Parameters

- **msgChannel`<X>`**: Ethernet channel number, range 1..32.
- **ethernetPort::<NetworkName>::<PortName>**: Ethernet port qualification.

## Selectors

- **status**: 
  - 0: Link down
  - 1: Link up
  - Type: long
  - Access Limitation: Read only

- **bitrate**: 
  - Bitrate in kBit/sec
  - Type: dword
  - Access Limitation: Read only

- **msgChannel**: 
  - Application channel, i.e. Eth 1
  - Type: word
  - Access Limitation: —

- **hwChannel**: 
  - Hardware channel. If not supported by network interface, value is 1.
  - Type: word
  - Access Limitation: Only with Vector Interfaces, i.e. VN5640, with operation mode with more than 1 hardware channel. Channel-based network access only

- **hwPort**: 
  - Port used for network-based access.
  - Type: ethernetPort
  - Access Limitation: [network-based](../../../CANoeCANalyzer/Ethernet/EthernetPortBasedNetworkAccess.md) access only

- **time_ns**: 
  - Timestamp of the status change
  - Type: int64
  - Access Limitation: Read only

- **medium**: 
  - 0: kEthernetPhyMediumUnknown
  - 1: kEthernetPhyMediumIEEE_802_3
  - 2: kEthernetPhyMedium100BASE_T1
  - 3: kEthernetPhyMedium1GB_COAX
  - 4: kEthernetPhyMedium1000BASE_T1
  - 5: kEthernetPhyMedium2500BASE_T1
  - 6: kEthernetPhyMedium5000BASE_T1
  - 7: kEthernetPhyMedium10000BASE_T1
  - 8: kEthernetPhyMedium10BASE_T1S
  - Type: enum EthernetPhyMedium
  - Access Limitation: Read only

- **mode**: 
  - 0: kEthernetPhyModeUnknown
  - 1: kEthernetPhyModeMaster
  - 2: kEthernetPhyModeSlave
  - Type: enum EthernetPhyMode
  - Access Limitation: Read only

- **connector**: 
  - 0: kEthernetPhyConnectorDefault (the only available connector on this channel)
  - 1: kEthernetPhyConnectorRJ45
  - 2: kEthernetPhyConnectorDSub
  - Type: enum EthernetPhyConnector
  - Access Limitation: Read only

## Example

```plaintext
on ethernetStatus *
{
  switch(this.status)
  {
    case 0:
      write("Ethernet link on Eth%d is down", this.msgChannel );
      break;
    case 1:
      write("Ethernet link on Eth%d is up with %dbit/sec", this.msgChannel , this.bitrate );
  }
}
```

[See Also](javascript:void(0);)