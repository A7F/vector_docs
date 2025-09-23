[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupMeasuredMethod.md)

## LookupMeasuredMethod (obsolete)

**CAPL Functions** » **Communication Objects** » **LookupMeasuredMethod**

**Valid for**: CANoe DE

### Function Syntax

```plaintext
measuredMethodRef * LookupMeasuredMethod(char[] path);
```

### Description

Searches for the specified measured method. The path must be complete including namespaces and both endpoints: `(Namespace::)+Service.measure[consumer,provider].Method`.

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the measured method.

### Return Values

The measured method. An uninitialized object if the method is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
measuredMethodRef MirrorAdjustment.Adjust adjustMethod;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char consumer[20] = "CANoe";
char provider[20] = "LeftMirror";
char method[20] = "Adjust";

snprintf(path, elcount(path), "%s.measure[%s,%s].%s", service, consumer, provider, method);
adjustMethod = (measuredMethodRef MirrorAdjustment.Adjust) lookupMeasuredMethod(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupMeasuredEvent](CAPLfunctionLookupMeasuredEvent.md) • [LookupConsumedMethod](CAPLfunctionLookupConsumedMethod.md)
