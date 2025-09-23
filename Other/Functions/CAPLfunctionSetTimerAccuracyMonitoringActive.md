# SetTimerAccuracyMonitoringActive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long SetTimerAccuracyMonitoringActive(msTimer timer, dword active);
```

## Description

With this function you can turn on an accuracy monitoring for a timer. If the monitoring is active, the real (wallclock) time which passes between the start of the timer and its execution is measured and can be read out with [GetLastTimerAccuracyNS](CAPLfunctionGetLastTimerAccuracyNS.md).

**Note**: A certain difference between realtime and simulation time is normal and not a problem in most cases. However, if you have higher realtime requirements, you may detect problems early by monitoring the accuracy of the important timers. Also note that with low busload, the simulation is calculated by default in a 1 ms interval, so that a difference of up to 1 ms is normal in such a situation.

## Parameters

- **timer**: The timer which shall be monitored.
- **active**: Whether monitoring shall be active (1) or inactive (0).

## Return Values

- **0**: Monitoring is now not active for the timer.
- **1**: Monitoring is now active for the timer.
- **-1**: Monitoring cannot be configured because of wrong execution mode. It is only possible to use the monitoring in real mode, not in simulated mode or in offline mode.

## Example

—

[Performance Monitor](../../../CANoeCANalyzer/Performance/PerformanceMonitor.md)
