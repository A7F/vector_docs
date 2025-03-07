[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/DistributedObjects/Methods/CAPLfunctionValueGetUpdateCount.md)

# valueHandle::GetUpdateCount

[CAPL Functions](../../CAPLfunctions.md) » [Distributed Objects](../CAPLfunctionsDOOverview.md) » valueHandle::GetUpdateCount

**Valid for:** CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Method Syntax

[dword valueHandle::GetUpdateCount();](../../../Shared/CAPL/General/ClassesAndObjects.md)

## Description

Returns the update count of the value. The update count is reset to zero at start of measurement and with each call to [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md). It is then increased each time the value is updated, even if the value does not change.

For some values, the count is only initialized when the value is accessed the first time for performance reasons. This means that if you want to use it as a ‘global’ count over the whole measurement, you should call [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md) at the start of the measurement explicitly.

## Parameters

—

## Return Values

The current update count.

## Example

```plaintext
MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.ResetValueState();
testWaitForTimeout(1000);
write("Updates during the last second: %d", MirrorAdjustment.consumerSide[CANoe,LeftMirror].CurrentPosition.GetUpdateCount());
```

[Programming with the Communication Concept (C#, Python and CAPL)](../../../CANoeCANalyzer/CommunicationConcept/Programming/CCP.md) • [valueHandle::GetChangeCount](CAPLfunctionValueGetChangeCount.md) • [valueHandle::ResetValueState](CAPLfunctionValueResetValueState.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)