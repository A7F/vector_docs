[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestModuleDescription.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestModuleDescription

# TestModuleDescription

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`TestModuleDescription (char description[]);`

## Description

With this function, a description text for the test module can be written into the report. The function can be called several times in a row, the transmitted texts are then added to one another without additional separation.

To obtain line breaks (in form of `<br />` tags) in the CANoe Test Report Viewer or HTML test report, "\n" may be inserted at any place. In case of XML/HTML format, the required replacement takes place during the transformation of the XML test report into an HTML file by means of an XSLT style sheet, where it can also be deactivated.

## Parameters

- **description**: Description text for the test module.

## Return Values

—

## Example

See example: [TestModuleTitle, TestModuleDescription](CAPLfunctionsTFSExampleTestModuleTitleTestModuleDescription.md)

[TestModuleTitle](CAPLfunctionTestModuleTitle.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)