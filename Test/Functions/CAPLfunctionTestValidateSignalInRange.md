# testValidateSignalInRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function replaces `testValidateSignalInRangeByTxNode`.

## Function Syntax

- `long testValidateSignalInRange (char aTestStep[], Signal aSignal, float aLowLimit, float aHighLimit); // form 1`
- `long testValidateSignalInRange (char aTestStep[], EnvVarName, float aLowLimit, float aHighLimit); // form 2`
- `long testValidateSignalInRange (char aTestStep[], sysvar aSysVar, float aLowLimit, float aHighLimit); // form 3`
- `long testValidateSignalInRange (char aTestStep[], sysvar aSysVar, int64 aLowLimit, int64 aHighLimit); // form 4`
- `long testValidateSignalInRange (char aTestStep[], ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit); // form 5`

## Description

Checks the value of the signal, the environment variable value or the system variable value against the condition:

`aLowLimit \<= Value \<= aHighLimit`

The test step is evaluated as either passed or failed depending on the results.

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTestStep**: Name of the test step for the test report
- **aSignal**: The signal to be polled
- **EnvVarName**: Environment variable to be queried
- **aSysVar**: System variable to be queried. May also be a specific element of a variable of type struct or generic array.

  **Note**  
  Not available for a single element of a double or integer array.

- **aLowLimit**: Lower limit of the value
- **aHighLimit**: Upper limit of the value

**Note**  
Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **-1**: General error
- **-2**: Type of the environment or system variable is not valid – only float or integer are valid- or invalid limits of the given range
- **0**: Correct functionality

## Example

```plaintext
// validates the value of the signal against the given range
long result;
result = testValidateSignalInRange("Check Velocity", Node_SUT::Velocity, 60, 100);
if (result != 0)
    TestStepFail("Error occurred!");
```
