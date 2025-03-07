[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxOutputPacketWithSignals.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxOutputPacketWithSignals

# AfdxOutputPacketWithSignals

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxOutputPacketWithSignals( long packet );
```

## Description

Sends a message and automatically updates the payload with the current Tx-signal values of the SignalServer.

**Note**

- There are conceptually two distinct ways to apply send specific signal values:
  - Use the Signal API methods to set the payload within the frame itself.
  - Use the Signal Server content to get the frame payload set (by this method or use [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md) with <initSignals> set to true).
- During PreStart-phase the SignalServer is not yet initialized.

## Parameters

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Return Values

- [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
variables
{
  long packet;
}

on preStart
{
  // initialize the frame header, don’t care for the payload
  packet  = AfdxInitPacket(0, "TESTMSG_ALLTYPES", 0 );
  if (packet == 0)
  {
    write( "<%NODE_NAME%> AfdxInitPacket failed due to:%s", errTxt );
  }
}

on key ‘1’
{
  // update payload with current tx-signal values from
  // signal server and then send the frame out
  AfdxOutputPacketWithSignals(packet);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)