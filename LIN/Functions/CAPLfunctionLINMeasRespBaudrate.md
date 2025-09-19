[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINMeasRespBaudrate.md)

**CAPL Functions** » **LIN** » **linMeasRespBaudrate**

# linMeasRespBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linMeasRespBaudrate(long frameID, int index);
```

## Description

With this function, it is possible to send a request to measure the baudrate value of a certain data byte of a certain LIN frame. The channel where the baudrate is measured is determined by the CAPL program context.

This function only initiates the baudrate measurement. The result becomes available when the next bus event for the specified ID occurs and it remains valid until the next measurement request. To retrieve the result, the function [linGetMeasBaudrate()](CAPLfunctionLINGetMeasBaudrate.md) shall be used.

**Note**: The baudrate can only be measured if the specified data byte contains at least one "0"-bit followed by a "1"-bit. This means that bytes with the following values cannot be measured:

- 0x0 (binary: 00000000)
- 0x80 (binary: 10000000)
- 0xC0 (binary: 11000000)
- 0xE0 (binary: 11100000)
- 0xF0 (binary: 11110000)
- 0xF8 (binary: 11111000)
- 0xFC (binary: 11111100)
- 0xFE (binary: 11111110)
- 0xFF (binary: 11111111)

## Parameters

- **frameID**: LIN frame identifier whose baudrate will be measured. Value range: 0…63
- **index**: Data byte index. Value range: 0..N, where N = length [in bytes] of specified LIN frame
  - [0..N-1]: data bytes 1..N
  - N: checksum byte

## Return Values

On successful request returns zero, otherwise -1.

## Example

Test case for measuring baudrate using certain data byte of a LIN frame.

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

[linSetBaudrate](CAPLfunctionLINSetBaudrate.md) • [linMeasHeaderBaudrate](CAPLfunctionLINMeasHeaderBaudrate.md) • [linGetMeasBaudrate](CAPLfunctionLINGetMeasBaudrate.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
