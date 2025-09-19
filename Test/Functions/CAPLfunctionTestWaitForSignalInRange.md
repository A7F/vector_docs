[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForSignalInRange.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForSignalInRange

# TestWaitForSignalInRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `long TestWaitForSignalInRange (sysvar aSysVar, float aLowLimit, float aHighLimit, dword aTimeout); // form 1`
- `long TestWaitForSignalInRange (dbEnvVar aEnvVar float aLowLimit, float aHighLimit, dword aTimeout); // form 2`
- `long TestWaitForSignalInRange (Signal aSignal, float aLowLimit, float aHighLimit, dword aTimeout); // form 3`
- `long TestWaitForSignalInRange (sysvar aSysVar, int64 aLowLimit, int64 aHighLimit, dword aTimeout); // form 4`
- `long TestWaitForSignalInRange (ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit, dword aTimeout); // form 5`

## Description

Checks the value of the signal, the system, or the environment variable against the condition:

`aLowLimit <= Value <= aHighLimit`

If this condition is already met when this function is called, it returns immediately without waiting.

The test step is evaluated as either passed or failed depending on the results.

## Parameters

- **aSysVar**: System variable to be queried. May also be a specific element of a variable of type struct or generic array.
  - Note: Not available for a single element of a double or integer array.
- **aEnvVar**: Environment variable to be queried.
- **aSignal**: Signal to be queried.
- **aLowLimit**: Lower limit of the value.
- **aHighLimit**: Upper limit of the value.
- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.

## Return Values

- **-1**: General error.
- **-2**: Type of the system/environment variable is not valid – only float or integer are valid — or signal or system variable is not valid or invalid limits of the given range.
- **0**: Wait state is exited due to a timeout.
- **1**: Wait state is exited due to condition fulfillment.

## Example

```c
// waits for a specified value range of signal or system variable ‘Velocity’
long result;
result = TestWaitForSignalInRange(Velocity, 80, 100, 2000);
```

[TestJoinSignalInRange](CAPLfunctionTestJoinSignalInRange.md) • [TestWaitForSignalOutsideRange](CAPLfunctionTestWaitForSignalOutsideRange.md)

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
