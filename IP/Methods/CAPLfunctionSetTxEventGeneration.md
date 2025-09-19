[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionSetTxEventGeneration.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::SetTxEventGeneration

# ethernetPacket::SetTxEventGeneration

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Method Syntax

void [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).SetTxEventGeneration( long enabled );

## Description

Enables/Disables the send-confirmation event generation for a packet which is send at the designated port. (Event generation is enabled by default).

**Note**  
Disabling the send-confirmation will result in not seeing the sender of the packet in the tool at all for the specific packet.

## Parameters

- **enabled**  
  0: if the ACK generation should be disabled.  
  1: if it should be enabled.

## Return Values

—

## Example

```plaintext
ethernetPacket txPacket;
int i;

txPacket.hwPort = ethernetPort::Ethernet1::ChatClient1;
txPacket.source = EthGetMacAddressAsNumber( "20:00:00:00:00:01" );
txPacket.destination = EthGetMacAddressAsNumber( "FF:FF:FF:FF:FF:FF" );
txPacket.Length = 100;
txPacket.type = 0xF123;
txPacket.SetTxEventGeneration(0); //Deactivate the ACK when sending the packet

for( i = 0; i < txPacket.Length; i++ )
{
  txPacket.Byte(i) = i & 0xFF;
}

output( txPacket );
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
