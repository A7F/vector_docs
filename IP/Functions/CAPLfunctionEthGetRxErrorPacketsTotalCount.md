[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetRxErrorPacketsTotalCount.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetRxErrorPacketsTotalCount**

# ethGetRxErrorPacketsTotalCount

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
qword ethGetRxErrorPacketsTotalCount(ethernetPort port);
```

## Description

Returns the number of received error packets of the specified port.

## Parameters

- **port**: Ethernet port.

## Return Values

Number of received error packets, **0** if no valid value currently exists.

## Example

```plaintext
void printStatistic(ethernetPort p)
{
  write("Port %s", p.name);
  write(" LinkSpeed          [Mbit/sec]: %lu [%lu ; %lu ; %lu]", ethGetLinkSpeed(p, eCurrValue), ethGetLinkSpeed(p, eMinValue), ethGetLinkSpeed(p, eAvgValue), ethGetLinkSpeed(p, eMaxValue));
  write(" RxPacketsTotalCount     [pkt]: %llu", ethGetRxPacketsTotalCount(p));
  write(" TxPacketsTotalCount     [pkt]: %llu", ethGetTxPacketsTotalCount(p));
  write(" RxPacketRate        [pkt/sec]: %llu [%llu ; %llu ; %llu]", ethGetRxPacketRate(p, eCurrValue), ethGetRxPacketRate(p, eMinValue), ethGetRxPacketRate(p, eAvgValue), ethGetRxPacketRate(p, eMaxValue));
  write(" TxPacketRate        [pkt/sec]: %llu [%llu ; %llu ; %llu]", ethGetTxPacketRate(p, eCurrValue), ethGetTxPacketRate(p, eMinValue), ethGetTxPacketRate(p, eAvgValue), ethGetTxPacketRate(p, eMaxValue));
  write(" RxErrorPacketTotalCount [pkt]: %llu", ethGetRxErrorPacketsTotalCount(p));
  write(" TxErrorPacketTotalCount [pkt]: %llu", ethGetTxErrorPacketsTotalCount(p));
  write(" RxBitRate           [bit/sec]: %llu [%llu ; %llu ; %llu]", ethGetRxBitRate(p, eCurrValue), ethGetRxBitRate(p, eMinValue), ethGetRxBitRate(p, eAvgValue), ethGetRxBitRate(p, eMaxValue));
  write(" TxBitRate           [bit/sec]: %llu [%llu ; %llu ; %llu]", ethGetTxBitRate(p, eCurrValue), ethGetTxBitRate(p, eMinValue), ethGetTxBitRate(p, eAvgValue), ethGetTxBitRate(p, eMaxValue));
  write(" RxBytesTotalCount      [byte]: %llu", ethGetRxBytesTotalCount(p));
  write(" TxBytesTotalCount      [byte]: %llu", ethGetTxBytesTotalCount(p));
  write(" SQI                          : %f [%f ; %f ; %f]", ethGetSQI(p, eCurrValue), ethGetSQI(p, eMinValue), ethGetSQI(p, eAvgValue), ethGetSQI(p, eMaxValue));
}

on key 'p'
{
  printStatistic(ethernetPort::Ethernet1::Port1);
}
```

[lookupEthernetPort](CAPLfunctionLookupEthernetPort.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
