[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetLastTimerAccuracyNS.md)

**CAPL Functions** » **General** » **Function Overview** » **GetLastTimerAccuracyNS**

# GetLastTimerAccuracyNS

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long GetLastTimerAccuracyNS(msTimer timer, int64& accuracy);
```

## Description

If you have turned on the accuracy monitoring for a timer with [SetTimerAccuracyMonitoringActive](CAPLfunctionSetTimerAccuracyMonitoringActive.md), you can read out the last measured accuracy when the timer has elapsed with this function. It returns the difference between the timer interval in simulation time and in real (wallclock) time in nanoseconds.

**Note:** A certain difference between realtime and simulation time is normal and not a problem in most cases. However, if you have higher realtime requirements, you may detect problems early by monitoring the accuracy of the important timers. Also note that with low busload, the simulation is calculated by default in a 1 ms interval, so that a difference of up to 1 ms is normal in such a situation.

## Parameters

- **timer**: The timer which shall be monitored.
- **accuracy**: The last measured accuracy in nanoseconds (out-parameter). If accuracy monitoring is active for the timer, but the timer has not yet elapsed, the value will be 0.

## Return Values

- **0**: Success
- **-1**: Accuracy monitoring is not active for the timer.

## Example

—

[Performance Monitor](../../../CANoeCANalyzer/Performance/PerformanceMonitor.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)