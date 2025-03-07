[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionValueResetValueState.md)

[CAPL Functions](../../CAPLfunctions.md) » [Communication Objects](../CAPLfunctionsCOOverview.md) » valueHandle::ResetValueState

# valueHandle::ResetValueState (obsolete)

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Method Syntax

[Method](../../../Shared/CAPL/General/ClassesAndObjects.md) Syntax

```
void valueHandle::ResetValueState();
```

## Description

Resets the state of the value:

- Sets the value to its initial value, if there is one defined
- Clears the change flag and the update flag
- Sets change count and update count to zero
- Sets last change and update time stamps to zero
- Sets the value state to 2 (offline value)

## Parameters

—

## Return Values

—

## Example

```plaintext
testcase MirrorTest1()
{
  // at the start of the testcase, reset all states
  MirrorAdjustment.consumerSide[0,0].CurrentPosition.ResetValueState();
  // ...
}
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [valueHandle::GetValueState](CAPLfunctionValueGetValueState.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)