[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSignalUpdate.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSignalUpdate

# TestWaitForSignalUpdate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForSignalUpdate (Signal aSignal, dword aTimeout);
```

## Description

Waits for an event from a signal.

## Parameters

- **aSignal**: Signal to be queried
- **aTimeout**: Maximum time that should be waited [ms].
  - Transmission of 0: no timeout controlling.

## Return Values

- **-2**: Signal is not valid
- **-1**: General error
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

## Example

```c
// waits 1000ms for update of signal "Velocity"
long result;
result = TestWaitForSignalUpdate(Node_SUT::Velocity, 1000);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)