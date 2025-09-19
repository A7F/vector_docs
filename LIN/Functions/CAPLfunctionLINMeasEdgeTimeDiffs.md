[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINMeasEdgeTimeDiffs.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linMeasEdgeTimeDiffs

# linMeasEdgeTimeDiffs

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `dword linMeasEdgeTimeDiffs(dword numIndices, long indices[]); // form 1`
- `dword linMeasEdgeTimeDiffs(dword numIndices, long indices[], dword id); // form 2`

## Description

This function activates the measurement of the falling edges of the specified bytes in the next frame with the correct **id** if specified. If the first form is used (without specifying an id), or by specifying the id **0xff/-1**, the measurement takes place in the next frame.

The measured values can be queried with [linGetMeasEdgeTimeDiffs](CAPLfunctionLINGetMeasEdgeTimeDiffs.md). The bitrates of the measured bytes can be queried via [linGetMeasByteBitRates](CAPLfunctionLINGetMeasByteBitRates.md).

## Parameters

- **numIndices**: The number of specified byte indices. A pending measurement may be canceled by specifying **numIndices=0**, before the frame to be measured occurs on the bus. A pending, uncompleted measurement must be canceled, before a new measurement can be activated.

- **indices**: An array containing the indices of the bytes to be measured. Note that the minimum size for this array is **numIndices**. The array is sorted ascending internally. Therefore, the results of the measurement are sorted as well from the lowest to the highest byte index. Furthermore, duplicate entries are ignored.

  - Index range:
    - -2...N, where N = length [in bytes] of specified LIN frame
    - -2: Sync field
    - -1: PID byte
    - 0...N-1: Data bytes 1...N
    - N: Checksum byte

- **id**: The LIN identifier of the frame to be measured. Value range: 0..63

  **Note**: If the function is configured to measure header bytes (index < 0) on interfaces of the XL family, the measurement always takes place in the next frame regardless of the specified id.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```c
// Test case for measuring edges of a number of data bytes of a LIN frame.
// Note: This test case can only be used in the context of test module nodes
testcase tcMeasureEdges(int byteIndex)
{
    long indices[1];
    float timeDiffs[4];
    dword numDiffs;
    indices[0] = byteIndex;
    // set request to measure the edges of the specified byte of the frame with ID=0x33
    linMeasEdgeTimeDiffs(1, indices, 0x33);
    // wait maximum 1000 [ms] for frame with ID=0x33
    waitResult = TestWaitForMessage(0x33, 1000);
    // declare failure if Wait has resumed not due to expected event
    if (1 != waitResult)
    {
        TestStepFail("Test1.1","Expected frame has not occurred during 1000 ms!");
    }
    // retrieve measured edges
    numDiffs = LINGetMeasEdgeTimeDiffs(4, timeDiffs);
    if (numDiffs == 0)
    {
        TestStepFail("Test1.1", "Failed to measure edges!");
    }
    else
    {
        TestStepPass("Test 1.1", "Edge measurement done...");
    }
}
```

[linGetMeasEdgeTimeDiffs](CAPLfunctionLINGetMeasEdgeTimeDiffs.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
