# valueHandle::GetChangeCount (obsolete)

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CommunicationObjects/Methods/CAPLfunctionValueGetChangeCount.md)

**CAPL Functions** » **Communication Objects** » valueHandle::GetChangeCount

**Valid for**: CANoe DE

## Method Syntax

```
dword valueHandle::GetChangeCount()
```

## Description

Returns the change count of the value. The change count is reset to zero at start of measurement and with each call to [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md). It is then increased each time the value changes (but not if it is updated with the same value).

For some values, the count is only initialized when the value is accessed the first time for performance reasons. This means that if you want to use it as a ‘global’ count over the whole measurement, you should call [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md) at the start of the measurement explicitly.

## Parameters

—

## Return Values

The current change count.

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.ResetValueState();
testWaitForTimeout(1000);
write("Changes during the last second: %d", MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.GetChangeCount());
```

## Related Links

- [Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md)
- [valueHandle::GetUpdateCount](CAPLfunctionValueGetUpdateCount.md)
- [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)
