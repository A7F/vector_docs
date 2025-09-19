# AfdxSetSignalInt

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetSignalInt( long packet, char signalName[], long value, long fdsStatus ); // form 1
long AfdxSetSignalInt( long packet, long offset, long value ); // form 2
```

## Description

This function sets the value of an integer signal.

## Parameters

- **packet**: Handle of the message.
- **signalName**: Name of the signal.
  - **Note**: The signal and its message need to be defined in the assigned DBC file.
- **offset**: The offset value points to the integer signal in the AFDX payload area.
- **value**: New integer value.
- **fdsStatus**:
  - 255: The status is not updated
  - [valid status enumeration](../../../CANoeCANalyzer/AFDX/afdxBasics/afdxFunctionalDataSet.md): The functional status is updated with this value.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
long packet;
long msgID = 0x1A112B73;

// create a new AFDX packet as defined in the DBC with this msgID
packet = AfdxInitPacket( msgID, NULL, 0 );

// set integer signal 1 to 78 degrees, don’t change status byte
AfdxSetSignalInt( packet, "VFG_OIL_TEMP_A_34", 78 );

// set float-signal 2 to 52 degree, set corresponding status to <NO>
AfdxSetSignalReal( packet, "VFG_OIL_TEMP_AB_32", 52, 3 );

// set boolean signal 3 to 1, set corresponding status to <NO>
AfdxSetSignalBool( packet, "VFG_OIL_TEMP_A_ON", 1, 3 );

// set enumeration signal 4 to 5, don’t change status byte
AfdxSetSignalInt( packet, "FLIGHT_GROUND_COND_3", 5 );

// set string signal 6 to hello, don’t change status byte
AfdxSetSignalString( packet, "TEST_STRING14_CITY", "hello" );

// set opaque signal 7 to 0x31,0x32,0x33, don’t change status byte
AfdxSetSignalOpaque( packet, "TEST_OPAQUE14_IDENT", 3, "123" );

AfdxOutputPacket( packet );
```
