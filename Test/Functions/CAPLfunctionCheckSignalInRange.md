[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionCheckSignalInRange.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) / [Signal Access](../../SignalAccess/CAPLfunctionsSignalAccessOverview.md) » checkSignalInRange

# checkSignalInRange

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**  
This function replaces `checkSignalInRangeByTxNode`.

## Function Syntax

- `long checkSignalInRange(Signal aSignal, float aLowLimit, float aHighLimit); // form 1`
- `long checkSignalInRange(EnvVarName, float aLowLimit, float aHighLimit); // form 2`
- `long checkSignalInRange(sysVar aSysVar, float aLowLimit, float aHighLimit); // form 3`
- `long checkSignalInRange(sysVar aSysVar, int64 aLowLimit, int64 aHighLimit); // form 4`
- `long checkSignalInRange(ServiceSignalNumber aSignal, float aLowLimit, float aHighLimit); // form 5`

## Description

Checks the signal value or the environment variable value or the system variable value against the condition:

`aLowLimit <= Value <= aHighLimit`

**Note**  
Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aSignal**: The signal to be polled.
- **EnvVarName**: Environment variable to be queried.
- **aSysVar**: System Variable to be queried. May also be a specific element of a variable of type struct or generic array.

  **Note**  
  Not available for a single element of a double or integer array.

- **aLowLimit**: Lower limit of the signal value.
- **aHighLimit**: Upper limit of the signal value.

**Note**  
Use the **int64 parameters** for system variables of UInt64 and Int64 type to cover the whole value range. The int64 parameter is interpreted for system variables of UInt64 type as qword (uint64).

## Return Values

- **1**: If the condition is TRUE
- **0**: If the condition is violated or the signal is unavailable, i.e. was not on the bus yet
- **-1**: General error
- **-2**: Type of the environment or system variable is not valid – only float or integer are valid - or invalid limits of the given range.

## Example

```c
// checks if the value of the signal is in the given range
long result;
result = checkSignalInRange(Node_SUT::Velocity, 60, 100);
if (result != 1)
    TestStepFail("Value of signal is not in the allowed range!");
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)