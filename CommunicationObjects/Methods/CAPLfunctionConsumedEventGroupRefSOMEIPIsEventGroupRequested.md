[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionConsumedEventGroupRefSOMEIPIsEventGroupRequested.md)

**CAPL Functions** » [Communication Objects](../CAPLfunctionsCOOverview.md) » consumedEventGroupRef::SOMEIPIsEventGroupRequested

# consumedEventGroupRef::SOMEIPIsEventGroupRequested (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Method Syntax

dword consumedEventGroupRef::SOMEIPIsEventGroupRequested();

## Description

Returns whether the specified event group is currently requested.

## Parameters

—

## Return Values

- **0**: Event group is not currently requested
- **1**: Event group is currently requested

## Example

```plaintext
val = MirrorAdjustment.consumerSide[CANoe,LeftMirror].AllEvents.SOMEIPIsEventGroupRequested();
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [consumedEventGroupRef::SOMEIPReleaseEventGroup](CAPLfunctionConsumedEventGroupRefSOMEIPReleaseEventGroup.md) • [consumedEventGroupRef::SOMEIPRequestEventGroup](CAPLfunctionConsumedEventGroupRefSOMEIPRequestEventGroup.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)