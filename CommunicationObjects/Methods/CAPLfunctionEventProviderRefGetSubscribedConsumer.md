[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionEventProviderRefGetSubscribedConsumer.md)

## eventProviderRef::GetSubscribedConsumer (obsolete)

**CAPL Functions** » **Communication Objects** » eventProviderRef::GetSubscribedConsumer

**Valid for**: CANoe DE

### Method Syntax

```plaintext
serviceConsumerRef * eventProviderRef::GetSubscribedConsumer(dword index);
```

### Description

Returns the subscribed consumer with the specified index.

### Parameters

- **index**: Index of the consumer. The condition `0 <= index < eventProviderRef::GetNrOfSubscribedConsumers` must be true.

### Return Values

The specified service consumer. An uninitialized object if the index is invalid.

### Example

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

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [eventProviderRef::GetNrOfSubscribedConsumers](CAPLfunctionEventProviderRefGetNrOfSubscribedConsumers.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
