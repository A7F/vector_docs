# on fct_returned (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`on fct_returned <function>;`

## Description

The event procedure is called at the consumer when a service function answer is returned to the consumer.

## Parameters

- **`<function>`**: Designates the function on which the event procedure shall react. This must be a combination of endpoints on consumer side.

## Selectors

See the [callContext](../Objects/CAPLfunctionCallContext.md) object.

## Example

```plaintext
on fct_returned MirrorAdjustment[CANoe,LeftMirror].Adjust
{
  write("Function result is %d", this.Result);
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [on fct_Calling](CAPLfunctionOnfctCalling.md) • [on fct_Called](CAPLfunctionOnfctCalled.md)
