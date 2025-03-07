[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupRxPDU.md)

## LookupRxPDU (obsolete)

**CAPL Functions** » **Communication Objects** » **LookupRxPDU**

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```plaintext
rxPDURef * LookupRxPDU(char[] path);
```

### Description

Searches for the specified rx PDU. The path must be complete including namespaces and endpoint(s):

- `(Namespace::)+PDU[Receiver]` for broadcast PDUs
- `(Namespace::)+PDU.receiverSide[Sender,Receiver]` for point-to-point PDUs

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the Rx PDU.

### Return Values

The Rx PDU. An uninitialized object if the PDU is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
rxPDURef MirrorState statePDU;
char path[200];
char pduName[50] = "Mirrors::MirrorState";
char receiver[20] = "CANoe";

snprintf(path, elcount(path), "%s[%s]", pduName, receiver);
statePDU = (rxPDURef MirrorState) lookupRxPDU(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupTxPDU](CAPLfunctionLookupTxPDU.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)