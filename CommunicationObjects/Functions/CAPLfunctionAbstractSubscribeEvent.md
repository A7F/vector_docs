[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionAbstractSubscribeEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » Abstract_SubscribeEvent

# Abstract_SubscribeEvent (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long Abstract_SubscribeEvent(consumedEventRef * event);
```

## Description

Subscribes for a service event if abstract binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedEventRef::AbstractRequestEvent](../Methods/CAPLfunctionConsumedEventRefAbstractRequestEvent.md) on the event.

## Parameters

- **event**: Event which shall be subscribed.

## Return Values

- **0**: Success
- **1**: Endpoint is not simulated
- **2**: Communication object does not use abstract binding
- **< 0**: Other error, e.g. event variable is not initialized

## Example

```plaintext
Abstract_SubscribeEvent(MirrorAdjustment.consumerSide[0,0].Position);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_UnsubscribeEvent](CAPLfunctionAbstractUnsubscribeEvent.md) • [SOMEIP_SubscribeEventGroup](CAPLfunctionSOMEIPSubscribeEventGroup.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)