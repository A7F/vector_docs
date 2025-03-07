[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionGetDrift.md)

# getDrift

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » getDrift

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
int getDrift();
```

## Description

Determines the constant deviation when Drift is set.

## Parameters

—

## Return Values

Drift in parts per thousand.

## Example

```plaintext
int val;
...
// Assign to val the Drift value
val = getDrift();
...
```

[getJitterMax](CAPLfunctionGetJitterMax.md) • [getJitterMin](CAPLfunctionGetJitterMin.md) • [setDrift](CAPLfunctionSetDrift.md) • [setJitter](CAPLfunctionSetJitter.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)