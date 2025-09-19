[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTCriticalUnlock.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostCriticalUnlock

# OnMostCriticalUnlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`OnMostCriticalUnlock();`

## Description

A "Critical Unlock" was detected on one of the configured MOST channels. This event occurs if the lock status of the connected MOST hardware does not exhibit a "Lock" (see MOST Spec 2V3 - 3.2.2 NetInterface) after a "Stable Lock" for at least t_Unlock (see MOST Spec 2V3 – 3.9 Timing Definitions). The relevant channel or time stamp of this event can be called up with the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

—

## Return Values

—

## Example

—

[OnMostStableLock](CAPLfunctionOnMOSTStableLock.md) • [mostGetLockEx](../Functions/CAPLfunctionMOSTGetLockEx.md) • [on mostLightLockError](CAPLfunctionOnMOSTLightLockError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
