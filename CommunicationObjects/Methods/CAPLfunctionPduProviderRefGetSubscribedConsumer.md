# pduProviderRef::GetSubscribedConsumer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

serviceConsumerRef * [pduProviderRef](../Objects/CAPLfunctionPDUProviderRef.md)::GetSubscribedConsumer(dword index);

## Description

Returns the subscribed consumer with the specified index.

## Parameters

- **index**: Index of the consumer. The condition `0 <= index < [pduProviderRef::GetNrOfSubscribedConsumers](CAPLfunctionPduProviderRefGetNrOfSubscribedConsumers.md)` must be true.

## Return Values

The specified service consumer. An uninitialized object if the index is invalid.

## Example

```plaintext
// output all subscribed consumers
dword i, nrOfConsumers;
serviceConsumerRef * consumer;
pduProviderRef * provider;

provider = MirrorAdjustment.providerSide[LeftMirror].StatusPdu;
nrOfConsumers = provider.GetNrOfSubscribedConsumers();
write("Nr of consumers is %d", nrOfConsumers);
for (i = 0; i < nrOfConsumers; ++i)
{
  consumer = provider.GetSubscribedConsumer(i);
  write("Consumer %d is %s", i, consumer.Name);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [pduProviderRef::GetNrOfSubscribedConsumers](CAPLfunctionPduProviderRefGetNrOfSubscribedConsumers.md)
