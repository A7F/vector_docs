[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINMeasHeaderBaudrate.md)

**CAPL Functions** » **LIN** » **linMeasHeaderBaudrate**

# linMeasHeaderBaudrate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long linMeasHeaderBaudrate(int index);
```

## Description

With this function, it is possible to set a request to measure the baudrate value for the next LIN header event. The channel, where the baudrate is measured, is determined by the CAPL program context.

This function only initiates the baudrate measurement. The result becomes available when the next LIN header occurs and it remains valid until the next measurement request. To retrieve the result, the function [linGetMeasBaudrate()](CAPLfunctionLINGetMeasBaudrate.md) shall be used.

**Note:**

- When LIN hardware is in Master mode, calling this function will have no effect.
- The baudrate can only be measured if the specified byte (PID or Sync Byte) contains at least one "0"-bit followed by a "1"-bit. This means that bytes with the following values cannot be measured:
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

- **index**: This parameter specifies a field of LIN header which will be used for baudrate measurement.
  - 0: Synch field
  - 1: Identifier field

## Return Values

On successful request returns zero, otherwise -1.

## Example

Test case for measuring baudrate using LIN header event

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

[linSetBaudrate](CAPLfunctionLINSetBaudrate.md) • [linGetMeasBaudrate](CAPLfunctionLINGetMeasBaudrate.md) • [linMeasRespBaudrate](CAPLfunctionLINMeasRespBaudrate.md)

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
