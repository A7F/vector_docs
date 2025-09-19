[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestInfoTable.md)

**CAPL Functions** » **Test Feature Set** » **TestInfoTable**

# TestInfoTable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

The user can display structured data in the report. The data is formatted as a table that can contain multiple rows and columns.

A header row can be specified by the function [TestInfoHeadingBegin](CAPLfunctionTestInfoHeadingBegin.md) and [TestInfoHeadingEnd](CAPLfunctionTestInfoHeadingEnd.md). Other table rows can be specified by the function [TestInfoRow](CAPLfunctionTestInfoRow.md). A row and a header row can be divided into multiple columns using the function [TestInfoCell](CAPLfunctionTestInfoCell.md).

The content of the table will be displayed using one of the test step functions: [TestStep, TestStepPass, TestStepFail, TestStepWarning](CAPLfunctionTestStep.md).

## Function Syntax

```
Long TestInfoTable (char[] description);
```

## Description

Creates a new table to display structured data in the report.

## Parameters

- **description**: Table description.

## Return Values

Handle to the newly created table. This handle must be passed to other related functions.

## Example

—

**Technical References are only available in English**

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
