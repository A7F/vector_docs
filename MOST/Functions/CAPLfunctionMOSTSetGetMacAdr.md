[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTSetGetMacAdr.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostSetMacAdr, mostGetMacAdr

# mostSetMacAdr, mostGetMacAdr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640, OptoLyzer G2 3150o, and OptoLyzer MOCCA compact 150c.

## Function Syntax

```plaintext
long mostSetMacAdr(long channel, int64 macAdr);
int64 mostGetMacAdr(long channel);
```

## Description

The functions set and retrieve the 48 bit MAC address of the network interface controller. The MAC address identifies the network node during Ethernet-over-MOST150 communication (see [OnMostEthPkt](../EventProcedures/CAPLfunctionOnMOSTEthPkt.md), [outputMostEthPkt](CAPLfunctionMOSTOutputMostEthPkt.md)).

## Parameters

- **channel**: Channel of the connected interface
- **macAdr**: 48 bit MAC address.

## Return Values

- **mostSetMacAdr**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)
- **mostGetMacAdr**: 
  - >=0: 48 bit MAC address
  - <0: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
// Set MAC address on channel MOST 1 to 01:02:03:04:05:06
mostSetMacAdr(1, 0x010203040506LL);
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostMacAdr](../EventProcedures/CAPLfunctionOnMOSTMacAdr.md) • [OnMostEthPkt](../EventProcedures/CAPLfunctionOnMOSTEthPkt.md) • [outputMostEthPkt](CAPLfunctionMOSTOutputMostEthPkt.md) • [mostSetNodeAdr](CAPLfunctionMOSTSetNodeAdr.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)