[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionLookupFieldProvider.md)

## LookupFieldProvider (obsolete)

**CAPL Functions** » **Communication Objects** » **LookupFieldProvider**

**Valid for**: CANoe DE

### Function Syntax

```plaintext
fieldProviderRef * LookupFieldProvider(char[] path);
```

### Description

Searches for the specified field provider. The path must be complete including namespaces, endpoint and field: `(Namespace::)Service[provider].field`.

You can downcast the result to a concrete type, see the example.

### Parameters

- **path**: Path of the field provider.

### Return Values

The field provider. An uninitialized object if the field provider is not found, which will also be reported in the Write Window or as an error in test system (if the function is called in a test routine).

### Example

```plaintext
fieldProviderRef MirrorAdjustment.Position positionField;
char path[200];
char service[50] = "Mirrors::MirrorAdjustment";
char provider[20] = "LeftMirror";
char fieldName[20] = "Position";

snprintf(path, elcount(path), "%s[%s].%s", service, provider, fieldName);
positionField = (fieldProviderRef MirrorAdjustment.Position) lookupFieldProvider(path);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [LookupEventProvider](CAPLfunctionLookupEventProvider.md) • [LookupFieldConsumer](CAPLfunctionLookupFieldConsumer.md)
