[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForRawSignalMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForRawSignalMatch

# TestWaitForRawSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `TestWaitForRawSignalMatch(dbSignal aSignal, int64 value, dword aTimeout); // form 1`
- `TestWaitForRawSignalMatch(char aSignalName[], int64 value, dword aTimeout); // form 2`
- `TestWaitForRawSignalMatch(dbSignal aSignal, byte data[], dword dataLength, dword aTimeout); // form 3`
- `TestWaitForRawSignalMatch(char aSignalName[], byte data[], dword dataLength, doword aTimeout); // form 4`

## Description

Checks the given raw value against the value of the signal. The resolution of the signal is considered.

If this condition is already met when this function is called, it returns immediately without waiting.

The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aSignal**: The signal.
- **aSignalName**: Name of the signal.
- **value**: Signal value to be set.
- **data**: The data bytes of the signal.
- **dataLength**: Length of the data.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

**Note**: The **int64** parameter is interpreted as **qword** and will be casted according to the signal type. If a byte comparison is required, a byte array should be used.

## Return Values

- **-1**: General error
- **-2**: Signal is not valid
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

## Example

```c
// waits for a specified value of signal ‘Velocity’
long result;
result = TestWaitForRawSignalMatch(Node_SUT::Velocity, 80, 1000);
```

[TestWaitForSignalMatch](CAPLfunctionTestWaitForSignalMatch.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
