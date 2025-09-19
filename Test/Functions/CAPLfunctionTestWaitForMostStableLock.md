[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostStableLock.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForMostStableLock**

# TestWaitForMostStableLock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestWaitForMostStableLock(dword aTimeout);
```

## Description

The function waits until the expiration of the time **aTimeout** for the occurrence of a LightLock event indicating "stable lock" state.

A LightLock event with a "stable lock" state is generated when a "light & Lock" state lasts uninterrupted at the hardware for a period of time equal or longer than tLock (see MOST specification).

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum wait time [ms] (Specification of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, f.e., functionality is not available
- **0**: Resume due to timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostCriticalUnlock](CAPLfunctionTestWaitForMostCriticalUnlock.md) • [TestWaitForMostLightOff](CAPLfunctionTestWaitForMostLightOff.md) • [TestWaitForMostShortUnlock](CAPLfunctionTestWaitForMostShortUnlock.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
