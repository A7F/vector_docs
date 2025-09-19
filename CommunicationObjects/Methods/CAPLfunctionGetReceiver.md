# GetReceiver (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetReceiver

**Valid for**: CANoe DE

## Method Syntax

- `COParticipant txSignalRef::GetReceiver();`
- `COParticipant rxSignalRef::GetReceiver();`
- `COParticipant txPDURef::GetReceiver();`
- `COParticipant rxPDURef::GetReceiver();`

## Description

Returns the receiver participant selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns a reference to that participant. Else returns an invalid reference.

## Example

—
