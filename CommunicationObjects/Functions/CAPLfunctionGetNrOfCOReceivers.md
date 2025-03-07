[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Functions/CAPLfunctionGetNrOfCOReceivers.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » GetNrOfCOReceivers

# GetNrOfCOReceivers (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword GetNrOfCOReceivers(communicationObject co);
```

## Description

Returns the current number of receiver endpoints at a signal or PDU communication object. Note the number of endpoints may vary over time for some objects. The function is particularly useful to iterate over all receivers.

## Parameters

- **co**: Communication object

## Return Values

The current number of receiver endpoints.

## Example

```plaintext
for (i = 0; i < GetNrOfCOReceivers(MirrorState); ++i)
{
  MirrorState.receiverSide[i].ResetValueState();
  // ...
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [GetNrOfCOConsumers](CAPLfunctionGetNrOfCOConsumers.md) • [GetNrOfCOProviders](CAPLfunctionGetNrOfCOProviders.md) • [GetNrOfCOSenders](CAPLfunctionGetNrOfCOSenders.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)