[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthGetLinkSpeed.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **ethGetLinkSpeed**

# ethGetLinkSpeed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
qword ethGetLinkSpeed(ethernetPort port, ValueSelector valueSelector);
```

## Description

Returns the link speed of the specified port. The parameter **valueSelector** controls whether the minimum value, the maximum value, the average value or the current value has to be returned.

## Parameters

- **port**: Ethernet port.
- **valueSelector**: Controls which value to return. The enumerator supports these values:
  - **eMinValue**: Returns the minimum value
  - **eMaxValue**: Returns the maximum value
  - **eAvgValue**: Returns the average value
  - **eCurrValue**: Return the current values

## Return Values

Link speed in [MBit/sec], **0** if no valid value currently exists.

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
