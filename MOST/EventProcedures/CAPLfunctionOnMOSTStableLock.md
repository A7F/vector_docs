[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTStableLock.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » OnMostStableLock

# OnMostStableLock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
OnMostStableLock();
```

## Description

A "Stable Lock" was detected on one of the configured MOST channels. This event occurs if the lock status of the connected MOST hardware exhibits "Lock" (see MOST Spec 2V3 - 3.2.2 NetInterface) for at least t_Lock (see MOST Spec 2V3 – 3.9 Timing Definitions). The relevant channel or time stamp of this event can be called up with the [mostEventChannel](../Functions/CAPLfunctionMOSTEvent.md), [mostEventTime](../Functions/CAPLfunctionMOSTEvent.md) and [mostEventOrigTime](../Functions/CAPLfunctionMOSTEvent.md) functions.

CAPL nodes are transparent to the controller events. Please use the Multibus Filter or MOST Filter, to filter these events in nodal sequences.

## Parameters

—

## Return Values

—

## Example

—

[OnMostCriticalUnlock](CAPLfunctionOnMOSTCriticalUnlock.md) • [mostGetLockEx](../Functions/CAPLfunctionMOSTGetLockEx.md) • [on mostLightLockError](CAPLfunctionOnMOSTLightLockError.md)
