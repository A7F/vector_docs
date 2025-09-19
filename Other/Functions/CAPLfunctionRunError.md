[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionRunError.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » runError

# runError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
void runError(long err, long);
```

## Description

Triggers a run error. Outputs the error number to the Write Window indicating the error number and the passed number, and then terminates the measurement.

## Parameters

Numbers that are represented in your CANoe DE product as a references for the user. The values under 1000 are reserved for internal purposes. The second parameter is reserved for future expansions.

## Return Values

—

## Example

```plaintext
...
if(rpm < 0) runError(1001,1);
...
```

[elCount](CAPLfunctionElCount.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
