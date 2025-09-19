[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/TCPIPAPI/Functions/CAPLfunctionIPGetAdapterChannel.md)

[CAPL Functions](../../CAPLfunctions.md) » [TCP/IP API](../CAPLfunctionsTCPIPOverview.md) » IpGetAdapterChannel

# IpGetAdapterChannel

Valid for:  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long IpGetAdapterChannel( dword ifIndex);
```

## Description

The function returns the number of the Ethernet channel (1 for Eth 1) to which the network adapter with the given index is attached.

## Parameters

- **ifIndex**: The 1-based network interface index.

## Return Values

The Ethernet channel number or 0 if the given **ifIndex** was invalid.

## Example

```plaintext
on start
{
  dword adapterCount;
  dword ifIndex;
  long channel;
  adapterCount = ipGetAdapterCount();

  for(ifIndex = 1; ifIndex <= adapterCount; ifIndex++)
  {
    channel = IpGetAdapterChannel (ifIndex);
    if(channel != 0)
    {
      write("Adapter %d is attached to channel %d", ifIndex, channel);
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
