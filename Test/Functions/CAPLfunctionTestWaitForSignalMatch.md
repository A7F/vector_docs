[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSignalMatch.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSignalMatch

# TestWaitForSignalMatch

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForSignalMatch (Signal aSignal, float aCompareValue, dword aTimeout); // form 1`
- `long TestWaitForSignalMatch (dbEnvVar aEnvVar, float aCompareValue, dword aTimeout); // form 2`
- `long TestWaitForSignalMatch (sysvar aSysVar, float aCompareValue, dword aTimeout); // form 3`
- `long TestWaitForSignalMatch (sysvar aSysVar, int64 aCompareValue, dword aTimeout); // form 4`
- `long TestWaitForSignalMatch (ServiceSignalNumber aSignal, float aCompareValue, dword aTimeout); // form 5`

## Description

Waits until the signal, the system variable or the environment variable matches the given value or the timeout is reached. The resolution of the signal is considered. If this condition is already met when this function is called, it returns immediately without waiting.

## Parameters

- **aSignal**: Signal to be queried.
- **aEnvVar**: Environment variable to be queried.
- **aSysVar**: System variable to be queried. May also be a specific element of a variable of type struct or generic array.  
  *Note*: Not available for a single element of a double or integer array.
- **aCompareValue**: Value which is compared to the signal value.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

*Note*: Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **-1**: General error
- **-2**: Signal or system variable is not valid
- **0**: Wait state is exited due to a timeout
- **1**: Wait state is exited due to condition fulfillment

## Example

```c
// waits for a specified value of signal or system variable ‘Velocity’
long result;
result = TestWaitForSignalMatch(Node_SUT::Velocity, 80, 1000);
```

[TestJoinSignalMatch](CAPLfunctionTestJoinSignalMatch.md) • [TestWaitForRawSignalMatch](CAPLfunctionTestWaitForRawSignalMatch.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)