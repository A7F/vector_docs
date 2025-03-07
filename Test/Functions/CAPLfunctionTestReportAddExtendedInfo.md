[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportAddExtendedInfo.md)

**CAPL Functions** » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportAddExtendedInfo

# TestReportAddExtendedInfo

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
TestReportAddExtendedInfo (char type[], char text[], ...);
```

## Description

With this function, it is possible to take over information into the protocol that is not subject to processing by a CANoe DE product. This way, for example, any HTML code can be copied directly into the protocol. A corresponding type specification specifies the type of information (e.g. HTML).

## Parameters

- **type**: Defined are the following types for the information text:
  - **html**: HTML code
  - **text**: Plain text without formatting instructions
  - **other**: Other text, taken over into the XML report, but not shown in the HTML report.

- **text**: Info text to be written into the report. The text can optionally contain values that are given as additional parameters. For that the corresponding format string can be inserted into the text and corresponding values are added to the parameter list. The format strings have the same meaning as with the [write](../../Other/Functions/CAPLfunctionWrite.md) function and are described there.

  **Example**:
  ```
  TestReportAddExtendedInfo("text", "Output voltage =  %d volts)", voltage);
  ```

  To obtain line breaks in CANoe Test Report Viewer or in HTML test report, "\n" may be inserted at any place. In case of XML/HTML format, the required replacement takes place during the transformation of the XML test report into an HTML file by means of an XSLT style sheet.

## Return Values

—

## Example

See example: [TestReportAdd* Functions](CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[TestReportAddImage](CAPLfunctionTestReportAddImage.md) • [TestReportAddMiscInfo](CAPLfunctionTestReportAddMiscInfo.md) • [TestReportAddMiscInfoBlock](CAPLfunctionTestReportAddMiscInfoBlock.md) • [TestReportAddEngineerInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSetupInfo](CAPLfunctionTestReportAddEngineerInfo.md) • [TestReportAddSUTInfo](CAPLfunctionTestReportAddEngineerInfo.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)