[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINGetMeasByteBitRates.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linGetMeasByteBitRates

# linGetMeasByteBitRates

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
dword linGetMeasByteBitRates(dword arrSize, float byteBitRates[]);
```

## Description

This function calculates the bitrates for every byte which has been selected for edge time measurement. It uses the received data as well as the measured edge differences. Therefore, the function [linMeasEdgeTimeDiffs](CAPLfunctionLINMeasEdgeTimeDiffs.md) must be called in advance. Note that for each measured byte a bitrate will be returned, although it might be 0 (this happens if there had been only one falling edge in the measured byte).

## Parameters

- **arrSize**: The size of the byteBitRates array.
- **byteBitRates**: The array which will receive the measured byte bitrates. The unit of the measured bitrates is bits/second.

## Return Values

Returns the number of bitrates copied into the byteBitRates-array.

## Example

```c
testcase ByteBitRatesTest()
{
  long indices[2] = { -2, -1 };
  float byteBitRates[2];
  dword numByteBitRates, i;
  char variableDesc[32];

  // start a new edge difference measurement for the next frame
  if (linMeasEdgeTimeDiffs(2, indices) == 0)
  {
    TestStepFail("ByteBitRatesTest", "Starting of edge measurement failed.");
    return;
  }

  // wait for any lin header
  if (testWaitForLinHeader(1000) != 1)
  {
    TestStepFail("ByteBitRatesTest", "No LIN header received within 1000 ms.");
    return;
  }

  // receive the measured bitrates
  numByteBitRates = linGetMeasByteBitRates(elCount(byteBitRates), byteBitRates);
  if (numByteBitRates != elCount(indices))
  {
    TestStepFail("ByteBitRatesTest", "Received implausible number of bitrates.");
    return;
  }
  for (i = 0; i < numByteBitRates; i++)
  {
    snprintf(variableDesc, elCount(variableDesc), "Bitrate of byte %d", indices[i]);
    testCaseReportMeasuredValue(variableDesc, byteBitRates[i], "bit/s");
  }
  TestStepPass("ByteBitRatesTest", "All byte bitrates have been received.");
}
```

[LinMeasEdgeTimeDiffs](CAPLfunctionLINMeasEdgeTimeDiffs.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
