# fieldProviderRef::GetSubscribedConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
serviceConsumerRef * fieldProviderRef::GetSubscribedConsumer(dword index);
```

## Description

Returns the subscribed consumer with the specified index.

## Parameters

- **index**: Index of the consumer. The condition `0 <= index < [fieldProviderRef::GetNrOfSubscribedConsumers](CAPLfunctionfieldProviderRefGetNrOfSubscribedConsumers.md)` must be true.

## Return Values

The specified service consumer. An uninitialized object if the index is invalid.

## Example

```plaintext
// output all subscribed consumers
dword i, nrOfConsumers;
serviceConsumerRef * consumer;
fieldProviderRef * provider;

provider = MirrorAdjustment.providerSide[LeftMirror].CurrentPosition;
nrOfConsumers = provider.GetNrOfSubscribedConsumers();
write("Nr of consumers is %d", nrOfConsumers);
for (i = 0; i < nrOfConsumers; ++i)
{
  consumer = provider.GetSubscribedConsumer(i);
  write("Consumer %d is %s", i, consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [fieldProviderRef::GetNrOfSubscribedConsumers](CAPLfunctionfieldProviderRefGetNrOfSubscribedConsumers.md)
