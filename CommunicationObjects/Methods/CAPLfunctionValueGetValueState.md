# valueHandle::GetValueState (obsolete)

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Method Syntax

```plaintext
dword valueHandle::GetValueState();
```

## Description

Returns the state of the value, which tells in particular whether it has already been updated once since the last call to [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md).

## Parameters

—

## Return Values

- **State of the value**
  - 0 – value not available or invalid
  - 1 – no value has been set yet
  - 2 – value was last set before the current measurement or the last call to [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md). The value may be the initial value if there is one defined.
  - 3 – value was set since the last call to [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)

## Example

```plaintext
long ret;
consumedEventRef * anEvent;
anEvent = lookupConsumedEvent(path);
if (anEvent.GetValueState() != 3) // not yet received
{
  anEvent.ClearUpdateFlag();
  ret = testWaitForUpdateFlag(anEvent, 200);
  // ...
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)
