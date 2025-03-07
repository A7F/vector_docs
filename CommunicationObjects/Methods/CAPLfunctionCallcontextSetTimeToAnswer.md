[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionCallcontextSetTimeToAnswer.md)

**CAPL Functions** » **Communication Objects** » **callcontext::SetTimeToAnswer**

# callcontext::SetTimeToAnswer (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

```plaintext
long callContext::SetTimeToAnswer(dword timeMs);
```

## Description

Tells the simulation when it shall return the answer for the call. The answer will be returned after the given time.

Note that you can also use the **AutoAnswerTimeNS** property of a method provider endpoint to set the answer delay for all following calls.

## Parameters

- **timeMs**: Relative time in milliseconds after which the call shall be returned.

## Return Values

—

## Example

```plaintext
on fct_Called MirrorAdjustment.providerSide[all,LeftMirror].Adjust
{
  this.Result = Mirrors::AdjustResult::OK;
  // return the call after 10 ms
  this.SetTimeToAnswer(10);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [callcontext::DeferAnswer](CAPLfunctionCallcontextDeferAnswer.md) • [callcontext::ReturnCall](CAPLfunctionCallcontextReturnCall.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)