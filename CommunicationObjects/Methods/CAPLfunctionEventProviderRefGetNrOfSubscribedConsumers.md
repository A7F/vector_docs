# eventProviderRef::GetNrOfSubscribedConsumers (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

dword [eventProviderRef](../Objects/CAPLfunctionEventProviderRef.md)::GetNrOfSubscribedConsumers();

## Description

Returns the number of currently subscribed consumers for the service event.

## Parameters

—

## Return Values

The number of currently subscribed consumers.

## Example

```plaintext
// output all subscribed consumers
dword i, nrOfConsumers;
serviceConsumerRef * consumer;
eventProviderRef * provider;

provider = MirrorAdjustment.providerSide[LeftMirror].CurrentPosition;
nrOfConsumers = provider.GetNrOfSubscribedConsumers();
write("Nr of consumers is %d", nrOfConsumers);
for (i = 0; i < nrOfConsumers; ++i)
{
  consumer = provider.GetSubscribedConsumer(i);
  write("Consumer %d is %s", i, consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [eventProviderRef::GetSubscribedConsumer](CAPLfunctionEventProviderRefGetSubscribedConsumer.md)
