[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionEventProviderRefTrigger.md)

## eventProviderRef::Trigger (obsolete)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » eventProviderRef::Trigger

**Valid for:** CANoe DE

### Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
void eventProviderRef::Trigger();
```

### Description

Triggers the specified event. This leads to a transmission of the event to all subscribed consumers without changing the current event value. The method is particularly useful for events which do not carry a value (have data type void).

### Parameters

—

### Return Values

—

### Example

```plaintext
MirrorAdjustment.providerSide[LeftMirror].CurrentPosition.Trigger();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [providedEventRef::Trigger](CAPLfunctionProvidedEventRefTrigger.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
