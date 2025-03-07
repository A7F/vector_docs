[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGenerateBusloadEthPkt.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGenerateBusloadEthPkt

# mostGenerateBusloadEthPkt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only available with MOST hardware VN2640.

## Function Syntax

```plaintext
long mostGenerateBusloadEthPkt(long channel, long pkts);
```

## Description

The function sends cyclical packets on the Ethernet channel. Use the [mostConfigureBusloadEthPkt](CAPLfunctionMOSTConfigureBusloadEthPkt.md) function to specify the send parameters and payload pattern.

## Parameters

- **channel**: Channel of the connected interface.
- **pkts**:
  - `0`: Stops the busload generation
  - `>0`: Sends the given number of packets
  - `-1`: Sends continual packets

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

Configure and start busload stress on keyboard event.

```plaintext
on key 's'
{
    long i, channel, rate, countertype, counterpos, datalen;
    int64 srcadr, destadr;
    byte data[1506];

    channel = 1;
    srcadr = -1LL; // use own MAC address as source
    destadr = 0x010203040506LL;
    rate = 50; // packets per second
    countertype = 4; // 4 byte counter
    counterpos = 9; // counter in byte6..byte9
    datalen = 300;

    // fill payload of stress packet
    for(i = 0; i < datalen; ++i)
        data[i] = (byte)i;

    // configure stress pattern
    mostConfigureBusloadEthPkt(channel, rate, countertype, counterpos, srcadr, destadr, datalen, data);

    // start generation of 500 packets
    mostGenerateBusloadEthPkt(channel, 500);
}
```

[mostConfigureBusloadEthPkt](CAPLfunctionMOSTConfigureBusloadEthPkt.md) • [OnMostStress](../EventProcedures/CAPLfunctionOnMOSTStress.md) • [mostSetMacAdr](CAPLfunctionMOSTSetGetMacAdr.md) • [outputMostEthPkt](CAPLfunctionMOSTOutputMostPkt.md) • [mostSetSBC](CAPLfunctionMOSTSetSBC.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)