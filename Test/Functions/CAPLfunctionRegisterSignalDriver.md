# RegisterSignalDriver

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long RegisterSignalDriver (Signal aSignal , char aCallbackFunction[]);
```

## Description

Registers the given callback as a 'signal driver' for the signal.

## Parameters

- **aSignal**: DB signal to be queried.
- **aCallbackFunction**: Name of a callback function that should be defined as follows: `void function(double value)`.

## Return Values

- **1**: Correct functionality
- **0**: CAPL 'signal driver' could not be registered

## Example

—
