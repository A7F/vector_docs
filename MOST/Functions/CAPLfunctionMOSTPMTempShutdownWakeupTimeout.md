[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTPMTempShutdownWakeupTimeout.md)

**CAPL Functions** » **MOST** » **mostPMTempShutdownWakeupTimeout**

# mostPMTempShutdownWakeupTimeout

**Valid for:** CANoe DE

## Function Syntax

```plaintext
long mostPMTempShutdownWakeupTimeout (long timeout);
```

## Description

As described in the MOST specification in the chapter "Over-Temperature Management", the [PowerMaster](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketPowerMaster.md) may try to wake-up the MOST ring, after a temperature shutdown, after a certain time. This function sets the timeout duration.

The default value is 60s.

**Note:** By setting the ["over temperature status"](CAPLfunctionMOSTPMSetOverTemperature.md) in the device of the [PowerMaster](../../../CANoeCANalyzer/MOST/MOSTSimulationApplicationSocketPowerMaster.md), the wake-up attempt will not be performed after the timeout. After resetting the "over temperature status" the application has to perform the wake-up, if necessary.

## Parameters

- **timeout**: Timeout in [ms].

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
