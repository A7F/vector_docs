[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Methods/CAPLfunctionHasProtocolError.md)

**CAPL Functions** » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » ethernetPacket::HasProtocolError

# ethernetPacket::HasProtocolError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

word [ethernetPacket](../Objects/CAPLfunctionEthernetPacket.md).HasProtocolError();

## Description

Returns 1, if the IP protocols of the Ethernet packet contains protocol errors, like wrong checksum or wrong length field, etc.  
Use [ethernetPacket::GetProtocolErrorText](CAPLfunctionGetProtocolErrorText.md) to get a description of the error.

## Parameters

—

## Return Values

- **0**: No protocol error detected
- **1**: Protocol error detected

## Example

```plaintext
on ethernetPacket *
{
  if (this.hasProtocolError())
  {
    char text[100];
    this.GetProtocolErrorText( text );
    write( "Protocol error on Eth %d: %s", this.msgChannel, text );
  }
}
```

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
