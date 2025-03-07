[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionSetstartdelay.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » setStartdelay

# setStartdelay

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void setStartdelay(int delay)
```

## Description

Sets the value of the Start Delay for this network node. This function can only be called in the preStart event procedure. Afterwards the value of the Start Delay **cannot** be changed any more.

## Parameters

- **delayText**: Integer for the Start Delay ms. This value may lie between 0 and 99999. If the value is greater or less than the limits of this range a warning appears in the Write Window.

## Return Values

—

## Example

```plaintext
...
on preStart
{
// Set Start Delay to 10 seconds
setStartdelay(10000);
}
```

[getStartdelay](CAPLfunctionGetStartDelay.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)