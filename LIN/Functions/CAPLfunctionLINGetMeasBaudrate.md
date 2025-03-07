[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetMeasBaudrate.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linGetMeasBaudrate

# linGetMeasBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
float linGetMeasBaudrate();
```

## Description

With this function, it is possible to retrieve results of a last baudrate measurement, which is done by calling [linMeasHeaderBaudrate()](CAPLfunctionLINMeasHeaderBaudrate.md) or [linMeasRespBaudrate()](CAPLfunctionLINMeasRespBaudrate.md) functions.

## Parameters

—

## Return Values

Returns the last measured baudrate [in bit/sec] or -1 on failure.

## Example

**Example 1**  
Test case for measuring baudrate using LIN header event. These test cases can only be used in the context of test module nodes.

```plaintext
testcase tcMeasureHeaderBaudrate ()
{
    long waitResult, measBaudrate;
    // set request to measure baudrate according to Synch field of a LIN header
    linMeasHeaderBaudrate(0);
    // wait maximum 1000 [ms] for LIN header with identifier 0x33
    waitResult = TestWaitForLinHeader(0x33, 1000);
    // declare failure if Wait has resumed not due to expected event
    if (1 != waitResult)
    {
        TestStepFail("Test 1.1","No LIN header with ID=0x33 occurred during 1000 ms!");
    }
    // retrieve measured baudrate
    measBaudrate = linGetMeasBaudrate();
    if (-1 == measBaudrate)
    {
        TestStepFail("Test 1.1", "Failed to measure header baudrate!");
    }
    TestStepPass("Test 1.1", "Header baudrate measurement done...");
}
```

**Example 2**  
Test case for measuring baudrate using certain data byte of a LIN frame. These test cases can only be used in the context of test module nodes.

```plaintext
testcase tcMeasureDatabyteBaudrate (int byteIndex)
{
    long waitResult, measBaudrate;
    // set request to measure baudrate using the specified byte of a frame with ID=0x33
    linMeasRespBaudrate(0x33, byteIndex);
    // wait maximum 1000 [ms] for a frame with ID=0x33
    waitResult = TestWaitForMessage(0x33, 1000);
    // declare failure if Wait has resumed not due to expected event
    if (1 != waitResult) {
        TestStepFail("Test 1.1","Expected frame has not occurred during 1000 ms!");
    }
    // retrieve measured baudrate
    measBaudrate = linGetMeasBaudrate();
    if (-1 == measBaudrate)
    {
        TestStepFail("Test 1.1", "Failed to measure response baudrate!");
    }
    TestStepPass("Test 1.1", "Response baudrate measurement done...");
}
```

[linMeasHeaderBaudrate](CAPLfunctionLINMeasHeaderBaudrate.md) • [linMeasRespBaudrate](CAPLfunctionLINMeasRespBaudrate.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)