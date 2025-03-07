[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionSOMEIPSubscribeEventGroup.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » SOMEIP_SubscribeEventGroup

# SOMEIP_SubscribeEventGroup (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long SOMEIP_SubscribeEventGroup(consumedEventGroupRef * eventGroup); // form 1`
- `long SOMEIP_SubscribeEventGroup(consumedServiceRef * service, char[] eventGroupName); // form 2`

## Description

Subscribes for a service event group if SOME/IP binding is used. Note that this is more **low-level**; usually it's more convenient to call [consumedEventGroupRef::SOMEIPRequestEventGroup](../Methods/CAPLfunctionConsumedEventGroupRefSOMEIPRequestEventGroup.md) on the event group.

## Parameters

- **eventGroup**: Event group which shall be subscribed.
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
SOMEIP_SubscribeEventGroup(MirrorAdjustment.consumerSide[0,0].AllEvents);
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [Abstract_SubscribeEvent](CAPLfunctionAbstractSubscribeEvent.md) • [SOMEIP_UnsubscribeEventGroup](CAPLfunctionSOMEIPUnsubscribeEventGroup.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)