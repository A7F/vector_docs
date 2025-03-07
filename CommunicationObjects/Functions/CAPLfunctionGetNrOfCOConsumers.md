[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionGetNrOfCOConsumers.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetNrOfCOConsumers

# GetNrOfCOConsumers (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```
dword GetNrOfCOConsumers(communicationObject co);
```

## Description

Returns the current number of consumer endpoints at a (service-oriented) communication object. Note the number of endpoints may vary over time for some objects. The function is particularly useful to iterate over all consumers.

## Parameters

- **co**: Communication object.

## Return Values

The current number of consumer endpoints.

## Example

```c
for (i = 0; i < GetNrOfCOConsumers(MirrorAdjustment); ++i)
{
  svc = MirrorAdjustment.providerSide[i,LeftMirror];
  // ...
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [GetNrOfCOProviders](CAPLfunctionGetNrOfCOProviders.md) • [GetNrOfCOSenders](CAPLfunctionGetNrOfCOSenders.md) • [GetNrOfCOReceivers](CAPLfunctionGetNrOfCOReceivers.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)