[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xStopScenario.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xStopScenario

# C2xStopScenario

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long C2xStopScenario();
```

## Description

This function stops the scenario execution immediately. The values of scenario attributes remain constant after the scenario stop. The scenario can be started again by calling [C2xStartScenario()](CAPLfunctionC2xStartScenario.md) CAPL function or manually in Scenario Manager Window.

## Parameters

—

## Return Values

- **1**: Scenario was successfully stopped.
- **0**: Scenario stop failed.
- **-1**: Error

## Example

```plaintext
on key 's'
{
  if (C2xStopScenario() == 1)
  {
    write("Scenario stopped");
  }
}

on key 'r'
{
  if (C2xStartScenario() == 1)
  {
    write("Scenario started");
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)