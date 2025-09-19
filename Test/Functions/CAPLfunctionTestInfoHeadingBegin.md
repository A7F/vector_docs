[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestInfoHeadingBegin.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestInfoHeadingBegin

# TestInfoHeadingBegin

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`TestInfoHeadingBegin (long handle, int indent);`

## Description

Starts a header row into a table. A header row can be divided into multiple columns using the function [TestInfoCell](CAPLfunctionTestInfoCell.md).

## Parameters

- **handle**: Handle to the table created by the function [TestInfoTable](CAPLfunctionTestInfoTable.md).
- **indent**: Level of indentation for the header row.

## Return Values

—

## Example

```plaintext
testcase StructuredDataSample()
{
  long table = 0;
  TestCaseDescription("Shows how to display a user-defined info table.");
  TestStepPass(0, "1", "First Step");

  // begin table
  table = TestInfoTable("User Structured Data");

  // header
  TestInfoHeadingBegin(table, 0);
  TestInfoCell(table, "Left part");
  TestInfoCell(table, "Operation");
  TestInfoCell(table, "Right part");
  TestInfoCell(table, "Result");
  TestInfoHeadingEnd(table);

  // row 1
  TestInfoRow(table, 0);
  TestInfoCell(table, "Frequency");
  TestInfoCell(table, "<");
  TestInfoCell(table, "50");
  TestInfoCell(table, "warning");

  // row 2
  TestInfoRow(table, 0);
  TestInfoCell(table, "Temperature");
  TestInfoCell(table, "in range");
  TestInfoCell(table, "90-100");
  TestInfoCell(table, "pass");

  // intermediate header
  TestInfoHeadingBegin(table, 1);
  TestInfoCell(table, "Additional conditions", 4);
  TestInfoHeadingEnd(table);

  // row 4
  TestInfoRow(table, 1);
  TestInfoCell(table, "Test Duration", 2);
  TestInfoCell(table, "60s");
  TestInfoCell(table, "fail");

  // output table
  TestStepFail(0, "2", table);
}
```

[TestInfoHeadingEnd](CAPLfunctionTestInfoHeadingEnd.md) • [TestInfoRow](CAPLfunctionTestInfoRow.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
