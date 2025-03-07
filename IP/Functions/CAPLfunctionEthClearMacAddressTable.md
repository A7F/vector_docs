[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionEthClearMacAddressTable.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethClearMacAddressTable

# ethClearMacAddressTable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long ethClearMacAddressTable( long channel);
```

## Description

Clears the MAC address table of the Ethernet network interface.

- In channel-based mode, the function can only be used with Vector network interface (e.g., VN5640) in operation mode which manages a MAC address table, i.e., Ethernet switch.
- In port-based mode, the function resets the tables of all switches within the network referenced by the channel number.

## Parameters

- **channel**: Ethernet channel number.  
  Value range: 1..32

## Return Values

- **0**: Success
- **1**: Not supported by network interface.
- **2**: Failed, check settings of network interface.
- **3**: Not supported in channel-based simulation mode.

## Example

```plaintext
on key '1'
{
  EthClearMacAddressTable( 1 ); // clear table on Eth 1
}
```

[See Also](javascript:void(0);)
```markdown
ethClearMacAddressTable|#aanchor3403||
ethDisableStatisticsOfAllNetworks|CAPLfunctionEthDisableStatisticsOfAllNetworks.htm#aanchor16238||
ethDisableStatisticsOfNetwork|CAPLfunctionEthDisableStatisticsOfNetwork.htm#aanchor15476||
ethDisableStatisticsOfPort|CAPLfunctionEthDisableStatisticsOfPort.htm#aanchor21071||
ethGetEthernetPortInfos|CAPLfunctionEthGetEthernetPortInfos.htm#aanchor24576||
ethGetLinkSpeed|CAPLfunctionEthGetLinkSpeed.htm#aanchor30517||
ethGetLinkStatus|CAPLfunctionEthGetLinkStatus.htm#aanchor11222||
ethGetMacAddressAsNumber|CAPLfunctionEthGetMacAddressAsNumber.htm#aanchor5705||
ethGetMacAddressAsString|CAPLfunctionEthGetMacAddressAsString.htm#aanchor24343||
ethGetPhyConnector|CAPLfunctionEthGetPhyConnector.htm#aanchor30259||
ethGetPhyMedium|CAPLfunctionEthGetPhyMedium.htm#aanchor12120||
ethGetPhyMode|CAPLfunctionEthGetPhyMode.htm#aanchor18718||
ethGetPhyState|CAPLfunctionEthGetPhyState.htm#aanchor23268||
ethGetRxBitRate|CAPLfunctionEthGetRxBitRate.htm#aanchor3137||
ethGetRxBytesTotalCount|CAPLfunctionEthGetRxBytesTotalCount.htm#aanchor4367||
ethGetRxErrorPacketsTotalCount|CAPLfunctionEthGetRxErrorPacketsTotalCount.htm#aanchor3642||
ethGetRxPacketRate|CAPLfunctionEthGetRxPacketRate.htm#aanchor12946||
ethGetRxPacketsTotalCount|CAPLfunctionEthGetRxPacketsTotalCount.htm#aanchor5448||
ethGetSQI|CAPLfunctionEthGetSQI.htm#aanchor451||
ethGetTxBitRate|CAPLfunctionEthGetTxBitRate.htm#aanchor23301||
ethGetTxBytesTotalCount|CAPLfunctionEthGetTxBytesTotalCount.htm#aanchor7286||
ethGetTxErrorPacketsTotalCount|CAPLfunctionEthGetTxErrorPacketsTotalCount.htm#aanchor28008||
ethGetTxPacketRate|CAPLfunctionEthGetTxPacketRate.htm#aanchor337||
ethGetTxPacketsTotalCount|CAPLfunctionEthGetTxPacketsTotalCount.htm#aanchor24314||
ethInjectPacket|CAPLfunctionEthInjectPacket.htm#aanchor16108||
ethResetStatistics|CAPLfunctionEthResetStatistics.htm#aanchor14440||
ethResetStatisticsOfAllNetworks|CAPLfunctionEthResetStatisticsOfAllNetworks.htm#aanchor14034||
ethResetStatisticsOfNetwork|CAPLfunctionEthResetStatisticsOfNetwork.htm#aanchor3246||
ethResetStatisticsOfPort|CAPLfunctionEthResetStatisticsOfPort.htm#aanchor9834||
ethSetLinkStatus|CAPLfunctionEthSetLinkStatus.htm#aanchor20510||
ethSetPhyState|CAPLfunctionEthSetPhyState.htm#aanchor29213||
ethStartPacketGenerator|CAPLfunctionEthStartPacketGenerator.htm#aanchor17264||
ethStopPacketGenerator|CAPLfunctionEthStopPacketGenerator.htm#aanchor14139||
GetServiceSignal|CAPLfunctionSomeIpGetServiceSignal.htm#aanchor10991||
GetServiceSignalData|CAPLfunctionSomeIpGetServiceSignalData.htm#aanchor3987||
GetServiceSignalString|CAPLfunctionSomeIpGetServiceSignalString.htm#aanchor25810||
output (Ethernet)|CAPLfunctionOutputEthernet.htm#aanchor4103||
SetServiceSignal|CAPLfunctionSomeIpSetServiceSignal.htm#aanchor11172||
SetServiceSignalData|CAPLfunctionSomeIpSetServiceSignalData.htm#aanchor2624||
SetServiceSignalString|CAPLfunctionSomeIpSetServiceSignalString.htm#aanchor5165
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)