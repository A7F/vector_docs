# TestWaitForSignalAvailable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
This function replaces `TestWaitForSignal` that has been available since version 5.1.

## Function Syntax

```plaintext
long TestWaitForSignalAvailable (Signal aSignal, dword aTimeout); // form 1
long TestWaitForSignalAvailable (ServiceSignal aSignal, dword aTimeout); // form 2
```

## Description

Tests the availability of a specific signal and waits if necessary until its availability.  
A signal that is received at least once from the bus after the measurement starts is classified as "available".

This function is useful when you want to assure that single signals are available before starting a signal-based test, i.e. to synchronize the tester with the bus.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous.  
Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aSignal**  
  Signal whose availability is being tested or for which is waited

- **aTimeout**  
  Maximum time that should be waited [ms].  
  Transmission of 0: no timeout controlling.

## Return Values

- **-2**  
  Wait state is exited due to a constraint/condition violation

- **-1**  
  General error, e.g. functionality is unavailable

- **0**  
  Wait state is exited due to a timeout

- **1**  
  Wait state is exited; signal is available for further tests

## Example

```plaintext
// waits for the occurrence of signal ‚EngineRunning’
long result;
result = TestWaitForSignalAvailable(EngineRunning, 2000);
```

[TestWaitForSignalsAvailable](CAPLfunctionTestWaitForSignalsAvailable.md)
