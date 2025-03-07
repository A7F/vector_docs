[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestValidateSignalOutsideRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » testValidateSignalOutsideRange

# testValidateSignalOutsideRange

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE •  CANoe:lite DE •  CANoe4SW DE •  CANoe4SW:lite DE

**Note**  
This function replaces `testValidateSignalOutsideRangeByTxNode`.

## Function Syntax

- `long testValidateSignalOutsideRange (char aTestStep[], Signal aSignal, float aLowLimit, float aHighLimit); // form 1`
- `long testValidateSignalOutsideRange (char aTestStep[], EnvVarName, float aLowLimit, float aHighLimit);  (effective with CANoe 6.0); // form 2`
- `long testValidateSignalOutsideRange (char aTestStep[], sysVar aSysVar, float aLowLimit, float aHighLimit); (effective with CANoe 7.0); // form 3`
- `long testValidateSignalOutsideRange (char aTestStep[], sysVar aSysVar, int64 aLowLimit, int64 aHighLimit); // form 4`
- `long testValidateSignalOutsideRange (char aTestStep[], ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit); // form 5`

## Description

Checks the signal value, the environment variable value or the system variable value against the condition:

- Value < aLowLimit or 
- Value > aHighLimit

The test step is evaluated as passed or failed depending on the results.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTestStep**: Name of the test step for the test report
- **aSignal**: The signal to be polled
- **EnvVarName**: Environment variable to be queried
- **aSysVar**: System Variable to be queried. May also be a specific element of a variable of type struct or generic array.

  **Note**  
  Not available for a single element of a double or integer array.

- **aLowLimit**: Lower limit of the value
- **aHighLimit**: Upper limit of the value

## Return Values

- **-1**: General error
- **-2**: Type of the environment or system variable is not valid – only float or integer are valid- or invalid limits of the given range
- **0**: Correct functionality

## Example

```plaintext
// validates the value of the signal against the given range
long result;
result = testValidateSignalOutsideRange("Check Velocity", Node_SUT::Velocity, 60, 100);
if (result != 0)
    TestStepFail("Error occurred!");
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)