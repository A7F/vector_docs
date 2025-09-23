# testWaitForHILAPISignalGeneratorFinished

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long testWaitForHILAPISignalGeneratorFinished(dword handle);
```

## Description

Waits until a running generator has finished.

## Parameters

- **handle**: Handle of the signal generator that shall be waited for.

## Return Values

- **\< 0**: An internal error occurred, e.g., a protocol error or a faulty configuration of the diagnostic layer.
- **1**: The event occurred.

## Example

```plaintext
HILAPIStartSignalGenerator(hGenerator);
testWaitForHILAPISignalGeneratorFinished(hGenerator);
```

[HILAPIStartSignalGenerator](CAPLfunctionHILAPIStartSignalGenerator.md)
