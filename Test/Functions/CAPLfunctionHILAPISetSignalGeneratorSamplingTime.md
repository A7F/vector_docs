# HILAPISetSignalGeneratorSamplingTime

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword HILAPISetSignalGeneratorSamplingTime(dword handle, dword samplingTimeMs);
```

## Description

By default, all signal generators work with a cycle time of one millisecond. This means that every millisecond a new signal value is calculated and written to the system variable assigned to the generator. By calling this function you can change this cycle time. To do this, you can call this function at any time (before the generator starts or while it is already running) and specify a new cycle time. The smallest possible cycle time is one millisecond.

Please note that this function can only be used for signal generators that actively output signal values. These are e.g. generators that stimulate a system variable. For signal generators that stimulate bus signals, the transmission behavior is already predetermined by the bus configuration. In this case, the Signal Generator does not work with a fixed cycle time, so that calling this function is not possible.

## Parameters

- **handle**: The handle of the Signal Generator.
- **samplingTimeMs**: The sampling time to set in milliseconds (must be \> 0).

## Return Values

- **0**: The sampling rate was set successfully.
- **!=0**: The sampling rate could not be set.

## Example

```c
dword generator;

// Load the signal description
generator = HILAPICreateSignalGenerator("MySignalDescription.sti");
testWaitForHILAPISignalGeneratorLoaded(generator);

// Assign the Signal Generator to a system variable
HILAPISetSignalGeneratorAssignment(generator, "MySignal", sysvar::MySysvar);

// Set the output interval of the generator to 5ms
HILAPISetSignalGeneratorSamplingTime(generator, 5);

// Run the generator and wait until finished
HILAPIStartSignalGenerator(generator);
testWaitForHILAPISignalGeneratorFinished(generator);

// Cleanup
HILAPIStopSignalGenerator(generator);
HILAPIDestroySignalGenerator(generator);
```

[HILAPICreateSignalGenerator](CAPLfunctionHILAPICreateSignalGenerator.md) • [HILAPIStartSignalGenerator](CAPLfunctionHILAPIStartSignalGenerator.md)
