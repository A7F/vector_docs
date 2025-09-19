# GetSenderIndex (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

- `long txSignalRef::GetSenderIndex();`
- `long rxSignalRef::GetSenderIndex();`
- `long txPDURef::GetSenderIndex();`
- `long rxPDURef::GetSenderIndex();`

## Description

Returns the sender index selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns the index of that endpoint. Else returns -1.

## Example

—
