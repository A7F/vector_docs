# GetReceiverIndex (obsolete)

**Valid for**: CANoe DE

## Method Syntax

- `long txSignalRef::GetReceiverIndex();`
- `long rxSignalRef::GetReceiverIndex();`
- `long txPDURef::GetReceiverIndex();`
- `long rxPDURef::GetReceiverIndex();`

## Description

Returns the receiver index selected for the CO reference.

## Parameters

—

## Return Values

If the object is valid and refers to an endpoint which is assigned to a participant, returns the index of that endpoint. Else returns -1.

## Example

—
