[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForHILAPISignalGeneratorLoaded.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » testWaitForHILAPISignalGeneratorLoaded

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

- **< 0**: An internal error occurred, e.g. a protocol error or a faulty configuration of the diagnostic layer.
- **1**: The event occurred.

## Example

```plaintext
hGenerator = HILAPICreateSignalGenerator("Example.sti");
testWaitForHILAPISignalGeneratorLoaded(hGenerator);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
