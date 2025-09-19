# GetSender (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `COParticipant txSignalRef::GetSender();`
- `COParticipant rxSignalRef::GetSender();`
- `COParticipant txPDURef::GetSender();`
- `COParticipant rxPDURef::GetSender();`

## Description

Returns the sender participant selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns a reference to that participant. Else returns an invalid reference.

## Example

—
