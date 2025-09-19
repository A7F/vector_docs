# AfdxGetSignalStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxGetSignalStatus( long packet, char signalName[] ); // form 1
long AfdxGetSignalStatus( long packet, long offset ); // form 2
```

## Description

This function returns the functional status (FS) of a signal.

## Parameters

- **packet**: Handle of the message.
- **signalName**: Name of the signal.  
  **Note:** The signal and its message need to be defined in the assigned DBC file.
- **offset**: The offset value points to a single byte in the 32-bit functional status area.

## Return Values

- [functional status value](../../../CANoeCANalyzer/AFDX/afdxBasics/afdxFunctionalDataSet.md)
- All other values indicate an [error code](../CAPLfunctionsAFDXErrorCodes.md).

## Example

**Analyze signals from an incoming AFDX packet using DBC information**

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
