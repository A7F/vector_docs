# SetSender (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

- `long txSignalRef::SetSender(char[] senderPath); // form 1`
- `long rxSignalRef::SetSender(char[] senderPath);`
- `long txPDURef::SetSender(char[] senderPath);`
- `long rxPDURef::SetSender(char[] senderPath);`

---

- `long txSignalRef::SetSender(dword senderIndex); // form 2`
- `long rxSignalRef::SetSender(dword senderIndex);`
- `long txPDURef::SetSender(dword senderIndex);`
- `long rxPDURef::SetSender(dword senderIndex);`

---

- `long txSignalRef::SetSender(COParticipant participant); // form 3`
- `long rxSignalRef::SetSender(COParticipant participant);`
- `long txPDURef::SetSender(COParticipant participant);`
- `long rxPDURef::SetSender(COParticipant participant);`

## Description

Sets the sender endpoint for the CO reference.

## Parameters

- **senderPath (form 1)**: Full path to a sender endpoint of the referenced object, including all namespaces.
- **senderIndex (form 2)**: 0-based index of a sender endpoint of the referenced object.
- **participant (form 3)**: A participant which contains a sender endpoint of the referenced object.

## Return Values

- **0**: Success
- **4**: Given endpoint is not of the referenced object (form 1)
- **5**: Given participant contains no fitting endpoint of the referenced object (form 3)
- **7**: Index is invalid (form 2)
- **9**: Trying to set a sender for a rxSignalRef or rxPDURef where the signal/PDU is for broadcast communication
- **-1**: Object is invalid

## Example

—
