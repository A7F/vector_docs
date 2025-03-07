[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionProvidedEventRefTrigger.md)

**CAPL Functions** » **Communication Objects** » **providedEventRef::Trigger**

# providedEventRef::Trigger (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```plaintext
void providedEventRef::Trigger();
```

## Description

Triggers the specified event. This leads to a transmission of the event to the specified consumer (if the consumer is subscribed) without changing the current event value. The method is particularly useful for events which do not carry a value (have data type **void**).

## Parameters

—

## Return Values

—

## Example

```plaintext
MirrorAdjustment.providerSide[CANoe,LeftMirror].CurrentPosition.Trigger();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [eventProviderRef::Trigger](CAPLfunctionEventProviderRefTrigger.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)