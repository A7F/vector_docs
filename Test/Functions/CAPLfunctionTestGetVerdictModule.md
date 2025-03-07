[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetVerdictModule.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetVerdictModule

# TestGetVerdictModule

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TestGetVerdictModule ();
```

## Description

Returns the current verdict out of the test module.

## Parameters

—

## Return Values

- **0**: pass
- **1**: fail
- **2**: none
- **3**: inconclusive
- **4**: error in test system

## Example

```plaintext
// gets the verdict of the test module and report it in the Write Window
void MainTest()
{
   MyTestCase();
   if (TestGetVerdictModule() == 1)
      Write("State of Test Module: failed.");
   else
      Write("State of Test Module: passed.");
}
```

[TestGetVerdictLastTestCase](CAPLfunctionTestGetVerdictLastTestCase.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)