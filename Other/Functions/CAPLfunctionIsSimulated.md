[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionIsSimulated.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » isSimulated

# isSimulated

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
long isSimulated();
```

## Description

This function is used to get the information if CANoe DE product is in simulated mode.

## Parameters

—

## Return Values

- **1**: True, CANoe DE product is in simulated mode.
- **0**: False, CANoe DE product is in real mode.

## Example

This example checks if CANoe DE product is in simulated mode. Then the test is not executed.

```c
// do not activate test when running in simulated mode
if (isSimulated())
{
    Write("Test cannot run in simulated mode!");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)