[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostCriticalUnlock.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostCriticalUnlock

# TestWaitForMostCriticalUnlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
