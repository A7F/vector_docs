[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/EventProcedures/CAPLfunctionOnfctCalling.md)

## CAPL Functions » Communication Objects » on fct_calling

# on fct_calling (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

### Function Syntax

```
on fct_calling <function>;
```

### Description

The event procedure is called when a service function is about to be called at a provider. At this time, the automatic answering feature has not yet set out parameters or delay, so you can still use the **ParamDefaults** or **DefaultResult** values to configure it.

### Parameters

- **<function>**: Designates the function on which the event procedure shall react. This must be a combination of endpoints on provider side, but the consumer endpoint can also be replaced by **all** to designate that the handler shall react on all consumer calls.

### Selectors

See the [callContext](../Objects/CAPLfunctionCallContext.md) object.

### Example

```plaintext
on fct_calling MirrorAdjustment[all,LeftMirror].Adjust
{
  if (abs(this.deltaX) > MAX_X || abs(this.deltaY) > MAX_Y)
  {
    $MirrorAdjustment.providerSide[all,LeftMirror].Adjust.DefaultResult = Mirrors::AdjustResult::OutOfRange;
  }
  else
  {
    $MirrorAdjustment.providerSide[all,LeftMirror].Adjust.DefaultResult = Mirrors::AdjustResult::OK;
  }
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on fct_Called](CAPLfunctionOnfctCalled.md) • [on fct_Returning](CAPLfunctionOnfctReturning.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)