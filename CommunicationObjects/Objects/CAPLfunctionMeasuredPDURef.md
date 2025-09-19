# measuredPDURef (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

- `measuredPDURef * <var>; // form 1`
- `measuredPDURef <PDU> <var>; // form 2`
- `measuredPDURef <Datatype> <var>; // form 3`

## Method Syntax

—

## Description

References a PDU measurement point, which means measuring a specific connection between sender and receiver for a PDU.

Not used for service PDUs, the data type of these is [measuredServicePDURef](CAPLfunctionMeasuredServicePDURef.md).

## Parameters

- **PDU**: PDU, determining the data type of the object.
- **Datatype**: data type of the object (a PDU definition).

## Selectors

- **Name**: Name of the measurement endpoint
  - Type: `char[]`
  - Access Limitation: Read only

- **Path**: Full path of the measurement endpoint (including namespaces)
  - Type: `char[]`
  - Access Limitation: Read only

- **SenderIndex**: Index of the sender. Note that the index may change if senders are added or removed.
  - Type: `dword`
  - Access Limitation: Read only

- **ReceiverIndex**: Index of the receiver. Note that the index may change if receivers are added or removed.
  - Type: `dword`
  - Access Limitation: Read only

## Example

```plaintext
measuredPDURef StatusPDU pdu1;
pdu1 = StatusPDU.measure[LeftMirror,CANoe];
write("Latest x: %d", $pdu1.Position.x);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [measuredServicePDURef](CAPLfunctionMeasuredServicePDURef.md)
