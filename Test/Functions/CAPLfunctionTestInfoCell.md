[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestInfoCell.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestInfoCell

# TestInfoCell

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void TestInfoCell (long handle, char[] text);`
- `void TestInfoCell (long handle, char[] text, int span);`

## Description

Adds a cell to a previously created row or header row.

Using this function, a row can be divided in several columns. For each column a separate cell must be added using this function.

The second version creates a cell that spans over several columns.

## Parameters

- **handle**: Handle to the table created by the function [TestInfoTable](CAPLfunctionTestInfoTable.md).
- **text**: Text to be displayed in the cell.
- **span**: Number of columns that a cell should span.

## Return Values

—

## Example

—

[TestInfoHeadingBegin](CAPLfunctionTestInfoHeadingBegin.md) • [TestInfoHeadingEnd](CAPLfunctionTestInfoHeadingEnd.md) • [TestInfoRow](CAPLfunctionTestInfoRow.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
