# GetNrOfCOProviders (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword GetNrOfCOProviders(communicationObject co);
```

## Description

Returns the current number of provider endpoints at a (service-oriented) communication object. Note the number of endpoints may vary over time for some objects. The function is particularly useful to iterate over all providers.

## Parameters

- **co**: Communication object

## Return Values

The current number of provider endpoints.

## Example

```c
for (i = 0; i < GetNrOfCOProviders(MirrorAdjustment); ++i)
{
  svc = MirrorAdjustment.consumerSide[CANoe,i];
  // ...
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [GetNrOfCOConsumers](CAPLfunctionGetNrOfCOConsumers.md) • [GetNrOfCOSenders](CAPLfunctionGetNrOfCOSenders.md) • [GetNrOfCOReceivers](CAPLfunctionGetNrOfCOReceivers.md)
