[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionsTFSExampleTestSetVerdictModule.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » Example: TestSetVerdictModule

# Example: TestSetVerdictModule

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

**Color usage**

- statements
- keywords
- comments
- test functions

```
// There are 3 test cases defined
testcase TestCase1() { /* ... */ }
testcase TestCase2() { /* ... */ }
testcase TestCase3() { /* ... */ }

// Test control
void MainTest() {
    long lVerdict1; // Remember the verdicts of all test cases
    long lVerdict2;
    longl Verdict3;

    TestCase1(); // mandatory test case - must be "pass"ed
    lVerdict1 = TestGetVerdictLastTestCase();

    // Only one of the following test cases must be passed
    TestCase2();
    lVerdict2 = TestGetVerdictLastTestCase();

    TestCase3();
    lVerdict3 = TestGetVerdictLastTestCase();

    if ( (lVerdict1 == 0) // mandatory
        && (lVerdict2 == 0 || lVerdict3 == 0)) // one of the set
    {
        TestSetVerdictModule(0); // Warning: Override verdict to pass
    }
    else
    {
        TestSetVerdictModule(1); // Warning: Override verdict to fail
    }
} // end MainTest
```
