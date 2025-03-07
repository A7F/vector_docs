[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxInitProtocol.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxInitProtocol

# AfdxInitProtocol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxInitProtocol( long packet, char protocolDesignator[] ); // form 1
long AfdxInitProtocol( long packet, char protocolDesignator[], char packetTypeDesignator[] ); // form 2
```

## Description

This function initializes the protocol for a packet. If necessary further needed lower protocols are initialized, e.g. IPv4. Already initialized higher protocols are deleted.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md).
- **packetTypeDesignator**: Type of the packet.

## Return Values

- **0**
- **other value**: See [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

```plaintext
testfunction Packet_InitProtocolICMP( long expectError, char expectErrorText[] )
{
  //
  // Create AFDX gPacket
  //
  gPacket_Result = AfdxInitProtocol( gPacket[gPacketSelect], "afdx", "icmp" );

  if (expectError == 0)
  {
    if (gPacket_Result != 0)
    {
      snprintf( gPacket_Text, elcount(gPacket_Text), "AfdxInitProtocol failed, result %d", gPacket_Result );
      TestStepFail( gPacket_Text );
      Packet_ReportLastError();
      return;
    }
    else
    {
      TestStepPass();
    }
  }
  else
  {
    if (Packet_CheckExpectError( "AfdxInitProtocol", expectError, expectErrorText ))
    {
      TestStepPass();
    }
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)