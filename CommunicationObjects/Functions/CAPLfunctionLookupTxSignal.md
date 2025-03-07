[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupTxSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » LookupTxSignal

# LookupTxSignal (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
txSignalRef * LookupTxSignal(char[] path);
```

## Description

Searches for the specified tx signal. The path must be complete including namespaces and endpoint(s):

- `(Namespace::)+Signal[Sender]` for broadcast signals
- `(Namespace::)+Signal.senderSide[Sender,Receiver]` for point-to-point signals

You can downcast the result to a concrete type, see the example.

## Parameters

- **path**: Path of the Tx signal.

## Return Values

The tx signal. An uninitialized object if the signal is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

## Example

```plaintext
txSignalRef long errorSignal;
char path[200];
char signalName[50] = "Mirrors::ErrorSignal";
char sender[20] = "LeftMirror";

snprintf(path, elcount(path), "%s[%s]", signalName, sender);
errorSignal = (txSignalRef long) lookupTxSignal(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupRxSignal](CAPLfunctionLookupRxSignal.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)