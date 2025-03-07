[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxGetMessageId.md)

[CAPL Functions](../../CAPLfunctions.md) » [AFDX](../CAPLfunctionsAFDXOverview.md) » AfdxGetMessageId

# AfdxGetMessageId

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetMessageId( long packet );
```

## Description

This function returns the [message ID](../../../CANoeCANalyzer/AFDX/afdxDBsupport/afdxDBsupportIntro.md) for the specified message. The ID is calculated from the actual addressing information of the message and the return value may be used to query more information about that message.

## Parameters

- **packet**: Handle of the message.

## Return Values

- **>0**: message ID
- **0**: error (invalid packet or no UDP)

## Example

Analyze signals from an incoming AFDX packet using DBC information

```plaintext
on preStart
{
  AfdxRegisterReceiveCallback("OnPacket");
}

void OnPacket( long dir, long line, int64 timestamp, long bag, long afdxFlags, long packet )
{
  long lVal=0; // integer signal
  long eVal=0; // enumeration signal
  long bVal=0; // boolean signal
  double rVal = 0.0; // float signal
  char sVal[16]; // string signal
  byte oVal[16]; // opaque signal
  long len, status, err;
  long msgID;
  char msgName[256];

  // get message ID of this message
  msgID = AfdxGetMessageId( packet );

  // get message name of this message
  err = AfdxGetMessageName( packet, 256, msgName );

  // get signal status
  status = AfdxGetSignalStatus( packet, "VFG_OIL_TEMP_A_34" );

  // get integer signal
  lVal = AfdxGetSignalInt( packet, "VFG_OIL_TEMP_A_34" );

  // get float-signal 2
  rVal = AfdxGetSignalReal( packet, "VFG_OIL_TEMP_AB_32" );

  // get boolean signal 3
  bVal = AfdxGetSignalBool( packet, "VFG_OIL_TEMP_A_ON" );

  // get enumeration signal 4
  eVal = AfdxGetSignalInt( packet, "FLIGHT_GROUND_COND_3" );

  // get string signal 6
  len = AfdxGetSignalString( packet, "TEST_STRING14_CITY", 16, sVal );

  // get opaque signal 7
  len = AfdxGetSignalOpaque( packet, "TEST_OPAQUE14_IDENT", 16, oVal );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)