# testWaitForHILAPISignalGeneratorLoaded

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long testWaitForHILAPISignalGeneratorLoaded(dword handle);
```

## Description

Waits until a signal generator created with [HILAPICreateSignalGenerator](CAPLfunctionHILAPICreateSignalGenerator.md) is fully loaded and ready to start.

## Parameters

- **handle**: Handle of the signal generator that shall be waited for.

## Return Values

- **\< 0**: An internal error occurred, e.g. a protocol error or a faulty configuration of the diagnostic layer.
- **1**: The event occurred.

## Example

```c
hGenerator = HILAPICreateSignalGenerator("Example.sti");
testWaitForHILAPISignalGeneratorLoaded(hGenerator);
```
