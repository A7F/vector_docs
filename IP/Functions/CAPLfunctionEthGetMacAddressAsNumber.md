[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetMacAddressAsNumber.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetMacAddressAsNumber**

# ethGetMacAddressAsNumber

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
qword ethGetMacAddressAsNumber( char macAddrStr[] );
```

## Description

Converts a MAC address string, i.e. "02:00:00:00:00:01", to a qword-number, which can be used with `ethernetPacket.source` and `ethernetPacket.destination`.

## Parameters

- **macAddrStr**: MAC address as string, i.e. "02:00:00:00:00:01".

## Return Values

The MAC address as qword or 0, if failed.

## Example

```plaintext
on key '1'
{
  ethernetPacket txPacket;
  txPacket.msgChannel = 1;
  txPacket.source      = ethGetMacAddressAsNumber( "20:00:00:00:00:01" );
  txPacket.destination = ethGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
  txPacket.Length      = 100;
  txPacket.type        = 0xF123;
  output( txPacket );
}
```

[See Also](javascript:void(0);)
- ethClearMacAddressTable
- ethDisableStatisticsOfAllNetworks
- ethDisableStatisticsOfNetwork
- ethDisableStatisticsOfPort
- ethGetEthernetPortInfos
- ethGetLinkSpeed
- ethGetLinkStatus
- ethGetMacAddressAsNumber
- ethGetMacAddressAsString
- ethGetPhyConnector
- ethGetPhyMedium
- ethGetPhyMode
- ethGetPhyState
- ethGetRxBitRate
- ethGetRxBytesTotalCount
- ethGetRxErrorPacketsTotalCount
- ethGetRxPacketRate
- ethGetRxPacketsTotalCount
- ethGetSQI
- ethGetTxBitRate
- ethGetTxBytesTotalCount
- ethGetTxErrorPacketsTotalCount
- ethGetTxPacketRate
- ethGetTxPacketsTotalCount
- ethInjectPacket
- ethResetStatistics
- ethResetStatisticsOfAllNetworks
- ethResetStatisticsOfNetwork
- ethResetStatisticsOfPort
- ethSetLinkStatus
- ethSetPhyState
- ethStartPacketGenerator
- ethStopPacketGenerator
- GetServiceSignal
- GetServiceSignalData
- GetServiceSignalString
- output (Ethernet)
- SetServiceSignal
- SetServiceSignalData
- SetServiceSignalString
