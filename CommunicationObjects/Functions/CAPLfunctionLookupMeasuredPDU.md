[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupMeasuredPDU.md)

## CAPL Functions » Communication Objects » LookupMeasuredPDU (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

### Function Syntax

```plaintext
measuredPDURef * LookupMeasuredPDU(char[] path);
```

### Description

Searches for the specified measured PDU. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.measure[consumer,provider].PDU`. You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the measured PDU.

### Return Values

The measured PDU. An uninitialized object if the PDU is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
measuredPduRef MirrorAdjustment.Status statusPDU;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char pduName[20] = "Status";

snprintf(path, elcount(path), "%s.measure[%s,%s].%s", service, consumer, provider, pduName);
statusPDU = (measuredPDURef MirrorAdjustment.Status) lookupMeasuredPDU(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupMeasuredEvent](CAPLfunctionLookupMeasuredEvent.md) • [LookupConsumedPDU](CAPLfunctionLookupConsumedPDU.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
