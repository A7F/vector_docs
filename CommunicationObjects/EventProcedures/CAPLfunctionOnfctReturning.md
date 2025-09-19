[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnfctReturning.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » on fct_returning

# on fct_returning (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
on fct_returning <function>;
```

## Description

The event procedure is called when a service function is about to return its answer at a provider. At this time, the automatic answering feature has already set the out parameters and return value to their default values if it is configured and the default answer time has elapsed.

The handler is particularly useful if the answer time is determined by another component.

## Parameters

- **`<function>`**: Designates the function on which the event procedure shall react. This must be a combination of endpoints on provider side, but the consumer endpoint can also be replaced by **all** to designate that the handler shall react on all consumer calls.

## Selectors

See the [callContext](../Objects/CAPLfunctionCallContext.md) object.

## Example

```plaintext
on fct_returning MirrorAdjustment[all,LeftMirror].Adjust
{
  if (abs(this.deltaX) > MAX_X || abs(this.deltaY) > MAX_Y)
  {
    this.Result = Mirrors::AdjustResult::OutOfRange;
  }
  else
  {
    this.Result = Mirrors::AdjustResult::OK;
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on fct_Calling](CAPLfunctionOnfctCalling.md) • [on fct_Called](CAPLfunctionOnfctCalled.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)