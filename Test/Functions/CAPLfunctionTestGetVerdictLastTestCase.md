[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetVerdictLastTestCase.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetVerdictLastTestCase

# TestGetVerdictLastTestCase

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long TestGetVerdictLastTestCase();
```

## Description

Returns the verdict of the last elapsed or current test case.

## Parameters

—

## Return Values

- **0**: pass
- **1**: fail
- **2**: none
- **3**: inconclusive
- **4**: error in test system

## Example

**Example 1**

```plaintext
// gets the verdict of last test case and report it in the Write Window
void MainTest()
{
   MyTestCase();
   if (TestGetVerdictLastTestCase() == 1)
      Write("MyTestCase failed.");
   else
      Write("MyTestCase passed.");
}
```

**Example 2**

See example: [TestSetVerdictModule](CAPLfunctionsTFSExampleTestSetVerdictModule.md)

[TestGetVerdictModule](CAPLfunctionTestGetVerdictModule.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)