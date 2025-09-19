# SetReceiver (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

- `long txSignalRef::SetReceiver(char[] receiverPath);` // form 1
- `long rxSignalRef::SetReceiver(char[] receiverPath);`
- `long txPDURef::SetReceiver(char[] receiverPath);`
- `long rxPDURef::SetReceiver(char[] receiverPath);`

---

- `long txSignalRef::SetReceiver(dword receiverIndex);` // form 2
- `long rxSignalRef::SetReceiver(dword receiverIndex);`
- `long txPDURef::SetReceiver(dword receiverIndex);`
- `long rxPDURef::SetReceiver(dword receiverIndex);`

---

- `long txSignalRef::SetReceiver(COParticipant participant);` // form 3
- `long rxSignalRef::SetReceiver(COParticipant participant);`
- `long txPDURef::SetReceiver(COParticipant participant);`
- `long rxPDURef::SetReceiver(COParticipant participant);`

## Description

Sets the receiver endpoint for the CO reference.

## Parameters

- **receiverPath (form 1)**: Full path to a receiver endpoint of the referenced object, including all namespaces.
- **receiverIndex (form 2)**: 0-based index of a receiver endpoint of the referenced object.
- **participant (form 3)**: A participant which contains a receiver endpoint of the referenced object.

## Return Values

- **0**: Success
- **4**: Given endpoint is not of the referenced object (form 1)
- **5**: Given participant contains no fitting endpoint of the referenced object (form 3)
- **7**: Index is invalid (form 2)
- **9**: Trying to set a receiver for a txSignalRef or txPDURef where the signal / PDU is for broadcast communication
- **-1**: Object is invalid

## Example

—
