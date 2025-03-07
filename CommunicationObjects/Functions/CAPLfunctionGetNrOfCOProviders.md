[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionGetNrOfCOProviders.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetNrOfCOProviders

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)