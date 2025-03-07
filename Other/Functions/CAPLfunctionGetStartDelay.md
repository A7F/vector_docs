[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetStartDelay.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getStartdelay

# getStartdelay

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`int getStartdelay();`

## Description

Determines the value of the start delay configured for this network node in the Simulation Setup.

## Parameters

—

## Return Values

Start delay in ms. If no start delay was set the function returns the value zero.

## Example

```c
int val;
...
// Assign to val the value of the start delay
val = getStartdelay();
...
```

[setStartdelay](CAPLfunctionSetstartdelay.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)