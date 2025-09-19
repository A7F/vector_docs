[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSignalOutsideRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSignalOutsideRange

# TestWaitForSignalOutsideRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForSignalOutsideRange (sysvar aSysVar, float aLowLimit, float aHighLimit, dword aTimeout); // form 1`
- `long TestWaitForSignalOutsideRange (dbEnvVar aEnvVar, float aLowLimit, float aHighLimit, dword aTimeout); // form 2`
- `long TestWaitForSignalOutsideRange (Signal aSignal, float aLowLimit, float aHighLimit, dword aTimeout); // form 3`
- `long TestWaitForSignalOutsideRange (sysvar aSysVar, int64 aLowLimit, int64 aHighLimit, dword aTimeout); // form 4`
- `long TestWaitForSignalOutsideRange (ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit, dword aTimeout); // form 5`

## Description

Checks the signal, the system or the environment variable value against the condition:

- Value < aLowLimit or
- Value > aHighLimit

If this condition is already met when this function is called, it returns immediately without waiting. The test step is evaluated as passed or failed depending on the results.

## Parameters

- **aSysVar**: System Variable to be queried. May also be a specific element of a variable of type struct or generic array.  
  **Note**: Not available for a single element of a double or integer array.

- **aEnvVar**: Environment variable to be queried.

- **aSignal**: Signal to be queried.

- **aLowLimit**: Lower limit of the value.

- **aHighLimit**: Upper limit of the value.

- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error.
- **-2**: Type of the system or environment variable is not valid – only float or integer are valid — or signal or system variable is not valid or invalid limits of the given range.
- **0**: Wait state is exited due to a timeout.
- **1**: Wait state is exited due to condition fulfilment.

## Example

```c
// waits for a specified value range of signal or system variable ‘Velocity’
long result;
result = TestWaitForSignalOutsideRange(Velocity, 80, 100, 2000);
```

[TestJoinSignalOutsideRange](CAPLfunctionTestJoinSignalOutsideRange.md) • [TestWaitForSignalInRange](CAPLfunctionTestWaitForSignalInRange.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
