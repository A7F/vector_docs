# SOMEIP_UnsubscribeEventGroup (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long SOMEIP_UnsubscribeEventGroup(consumedEventGroupRef * eventGroup); // form 1`
- `long SOMEIP_UnsubscribeEventGroup(consumedServiceRef * service, char[] eventGroupName); // form 2`

## Description

Unsubscribes for a service event group if SOME/IP binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedEventGroupRef::SOMEIPReleaseEventGroup](../Methods/CAPLfunctionConsumedEventGroupRefSOMEIPReleaseEventGroup.md) on the event group.

## Parameters

- **eventGroup**: Event group which shall be unsubscribed.
- **service**: Service which contains the event group.
- **eventGroupName**: Name of the event group.

## Return Values

- **0**: Success
- **1**: Service object is not initialized
- **2**: Communication object does not use SOME/IP binding
- **3**: Event group not found
- **< 0**: Other error, e.g., event variable is not initialized

## Example

```plaintext
SOMEIP_UnsubscribeEventGroup(MirrorAdjustment.consumerSide[0,0].AllEvents);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_UnsubscribeEvent](CAPLfunctionAbstractUnsubscribeEvent.md) • [SOMEIP_SubscribeEventGroup](CAPLfunctionSOMEIPSubscribeEventGroup.md)
