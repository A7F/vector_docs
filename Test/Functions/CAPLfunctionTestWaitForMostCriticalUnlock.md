# TestWaitForMostCriticalUnlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long TestWaitForMostCriticalUnlock(dword aTimeout);
```

## Description

The function waits until the expiration of the time **aTimeout** for the occurrence of a LightLock event indicating "critical unlock" state.

A LightLock event with a "critical unlock" state is generated, when a single "Light & no Lock" state occurs after a "stable lock" state and lasts longer than tUnlock (see MOST specification), or several "light, no lock" states occur successively and add up to a duration longer than tUnlock.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum wait time [ms] (Specification of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, f.e. functionality is not available
- **0**: Resume due to timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostLightOff](CAPLfunctionTestWaitForMostLightOff.md) • [TestWaitForMostShortUnlock](CAPLfunctionTestWaitForMostShortUnlock.md) • [TestWaitForMostStableLock](CAPLfunctionTestWaitForMostStableLock.md)
