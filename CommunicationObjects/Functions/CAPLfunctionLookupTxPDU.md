[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupTxPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupTxPDU

# LookupTxPDU (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
txPDURef * LookupTxPDU(char[] path);
```

## Description

Searches for the specified tx PDU. The path must be complete including namespaces and endpoint(s):

- `(Namespace::)+PDU[Sender]` for broadcast PDUs
- `(Namespace::)+PDU.senderSide[Sender,Receiver]` for point-to-point PDUs

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the Tx PDU.

## Return Values

The tx PDU. An uninitialized object if the PDU is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```c
txPDURef MirrorState statePDU;
char path[200];
char pduName[50] = "Mirrors::MirrorState";
char sender[20] = "LeftMirror";

snprintf(path, elcount(path), "%s[%s]", pduName, sender);
statePDU = (txPDURef MirrorState) lookupTxPDU(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupRxPDU](CAPLfunctionLookupRxPDU.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)