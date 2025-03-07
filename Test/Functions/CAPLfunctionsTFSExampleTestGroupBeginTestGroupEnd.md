[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionsTFSExampleTestGroupBeginTestGroupEnd.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » Example: TestGroupBegin, TestGroupEnd

# Example: TestGroupBegin, TestGroupEnd

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Color usage**

- statements
- keywords
- comments
- test functions

```
MainTest()
{
    // open first test group
    TestGroupBegin("Test Mode Configuration", "Test cases concerning the build-in test mode.");
    ConfigureSUT_Testmode(); // test cases of first test group
    Toggle_Testmode();
    SwitchOff_Testmode();
    TestGroupEnd(); // end of first test group

    // open second test group
    TestGroupBegin("Management Functions", "Test cases concerning all management abilities.");
    Check_ManagementFlag(); // test case is part of second test group

    // open nested test group
    TestGroupBegin("Power Management", "");
    PowerUp(); // test cases of nested test group
    PowerDown();
    TestGroupEnd(); // end of nested test group

    // open second nested test group
    TestGroupBegin("Temperature Management", "");
    NormalTemp(); // test cases of second nested test group
    OverTemperature();
    TestGroupEnd(); // end of second nested test group

    TestGroupEnd(); // end of second test group
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)