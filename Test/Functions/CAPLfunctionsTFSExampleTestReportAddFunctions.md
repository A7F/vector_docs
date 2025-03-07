[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionsTFSExampleTestReportAddFunctions.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » Example: TestReportAdd* Functions

# Example: TestReportAdd* Functions

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Color usage**

- statements
- keywords
- comments
- test functions

```plaintext
MainTest()
{
    ...
    // add information to SUT information table
    TestReportAddSUTInfo("Serial No.", "A012345BC");
    TestReportAddSUTInfo("Manufactured", "2003-10-02");
    // add information to test engineer information table
    TestReportAddEngineerInfo("Test Engineer", "S. Grey");
    TestReportAddEngineerInfo("Stuff No.", "12345");
    // add information to test setup information table
    TestReportAddSetupInfo("Tester", "TH12");
    ...
    // add html line to report, e.g. a link to the homepage
    TestReportAddExtendedInfo("html", "<A HREF=\"http://www.vector.com\">Homepage</A>");
    ...
}

testcase Configure_Powermanagement ()
{
    ...
    // add info block to test case in report
    TestReportAddMiscInfoBlock("Used Test Parameters");
    TestReportAddMiscInfo("Max. voltage", "19.5 V");
    TestReportAddMiscInfo("Max. current", "560 mA");
    ...
    // add image to report, scale down to reasonable size
    TestReportAddImage("Oscilloscope Snapshot", "osc_01.png", "400px", "");
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)