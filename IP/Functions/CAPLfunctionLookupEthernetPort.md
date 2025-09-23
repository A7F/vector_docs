[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionLookupEthernetPort.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » lookupEthernetPort

# lookupEthernetPort

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
ethernetPort lookupEthernetPort(char[] ethernetPortName);
```

## Description

Gets the Ethernet port for a port qualification string.

## Parameters

- **ethernetPortName**: The port qualification string `<NetworkName>::<PortName>`.

## Return Values

Ethernet port

## Example

```plaintext
on ethernetPacket *
{
  if (this.hwPort == lookupEthernetPort("Ethernet1::ChatClient1"))
  {
    write("Received a packet on %s", "Ethernet1::ChatClient1");
  }
}
```
