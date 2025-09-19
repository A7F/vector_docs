[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthResetStatisticsOfAllNetworks.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethResetStatisticsOfAllNetworks

# ethResetStatisticsOfAllNetworks

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```c
void ethResetStatisticsOfAllNetworks();
```

## Description

Resets the RT statistic values of all ports of all Ethernet networks. It will not influence the Statistic Window or the system variables.

## Parameters

—

## Return Values

—

## Example

```c
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

on key '0'
{
  ethResetStatisticsOfAllNetworks();
}

on key '1'
{
  ethResetStatisticsOfNetwork(ethernetport::Ethernet2::ECU_3);
}

on key '2'
{
  ethResetStatisticsOfPort(ethernetport::Ethernet1::ECU_2);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
