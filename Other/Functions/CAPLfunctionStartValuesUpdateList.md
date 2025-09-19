[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionStartValuesUpdateList.md)

**CAPL Functions** » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » startValuesUpdateList

# startValuesUpdateList

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Note

- Call `startValuesUpdateList()` in the `on stopMeasurement` CAPL event handler to save the last variable or signal values, for which start values are defined, for the next measurement start.
- If you change the value of a variable or signal value in a CAPL event handler, you cannot call `startValuesUpdateList()` in the same handler to save the values just set as start values. The variable or signal value is only changed after the function call `startValuesUpdateList()`. Decouple the call to `startValuesUpdateList()` via a timer from setting the variable or signal value. Refer to example 2 below.

## Function Syntax

```plaintext
void startValuesUpdateList(); // form 1
void startValuesUpdateList(char groupName[]); // form 2
void startValuesUpdateList(char groupName[], long onlyActiveStartValues); // form 3
```

## Description

Sets the start values of variables/signals in the CANoe DE product [Start Value Window](../../../CANoeCANalyzer/Windows/StartValues/StartValuesWindow.md) to the currently measured values.

## Parameters

- **groupName**: Name of a group containing start values. If `groupName` is defined, then only the active start values contained in this group get the currently measured values. If `groupName` is not defined or is equal to "", then only the active start values of all groups get the currently measured values.

- **onlyActiveStartValues**: Determines if active start values get the currently measured values or not. If missing, then only the active start values are considered.
  - `1`: Only the active start values get the currently measured values.
  - `0`: All start values (active and inactive) get the currently measured values.

## Return Values

—

## Example

### Example 1

```plaintext
on key '1'
{
  startValuesUpdateList("Start values group1");
}

on key '2'
{
  startValuesUpdateList();
}

on key '3'
{
  startValuesUpdateList(""); // corresponds to startValuesUpdateList();
}

on key '4'
{
  startValuesUpdateList("Start values group1", 1);
}

on stopMeasurement
{
  startValuesUpdateList();
}
```

### Example 2

```plaintext
variables
{
  msTimer t;
}
on timer t
{
  startValuesUpdateList();
}
on key '5'
{
  @myVariable = 123;

  //startValuesUpdateList();    // this call would not save the value 123 of myVariable
  //because the variable is set later than the function call is executed.

  setTimer(t, 0);
}
```

[startValuesUpdateSymbols](CAPLfunctionStartValuesUpdateSymbols.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
