[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostShortUnlock.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostShortUnlock

# TestWaitForMostShortUnlock

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestWaitForMostShortUnlock(dword aTimeout);
```

## Description

The function waits until the expiration of the time **aTimeout** for the occurrence of a LightLock event indicating "Light & no Lock" state.

A LightLock event with a "Light & no Lock" state is generated when there is no interpretable signal at the Optical Receiver (FOR) of the hardware for a brief moment (< tUnlock, see also MOST specification) and the ring has been in a "Light & Lock" state previously.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum wait time [ms] (Specification of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, e.g., functionality is not available
- **0**: Resume due to timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostCriticalUnlock](CAPLfunctionTestWaitForMostCriticalUnlock.md) • [TestWaitForMostLightOff](CAPLfunctionTestWaitForMostLightOff.md) • [TestWaitForMostStableLock](CAPLfunctionTestWaitForMostStableLock.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
