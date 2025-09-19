[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestReportAddImage.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestReportAddImage

# TestReportAddImage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

**Note**

In case the XML/HTML report output format is selected, the image should be in JPEG, GIF or PNG format since during the transformation to HTML only the reference to the file is written in the HTML file and the common HTML browsers generally only support these file formats for images.

In case of CANoe Test Report Viewer format the images will be directly embedded within the report files.

## Function Syntax

`TestReportAddImage (char description[], char filename[]); // form 1`

`TestReportAddImage (char description[], char filename[], char width[], char height[]); // form 2`

## Description

With this function the reference to a file that contains an image can be taken over into the protocol. This command can be used in the context of the test module and also in the context of a test case.

The existence of the file is not checked.

A file path or URL can be provided for the image. Relative file paths are based on the folder that contains the XML report. If backslashes are used as separators, a double backslash ('\\') must be used to separate directories within the path.

The second variant of this function allows to set the width and/or height with which the image should be displayed in the report. If width or height is specified, the HTML report will automatically show the picture with a link which opens the picture in full size in a new window. The width and height parameters are transferred to the HTML report, their values can be given as pixels or percentage. See an HTML reference for details.

## Parameters

- **description**: Description text for the picture
- **filename**: Name of the picture file, possibly with path specification
- **width**: Width of the image.
- **height**: Height of the image.

## Return Values

—

## Example

See example: [TestReportAdd* Functions](CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[TestReportAddExtendedInfo](CAPLfunctionTestReportAddExtendedInfo.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
