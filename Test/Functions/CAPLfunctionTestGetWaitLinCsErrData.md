[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestGetWaitLinCsErrData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestGetWaitLinCSErrorData

# TestGetWaitLinCSErrorData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestGetWaitLinCSErrorData (linCSError apEvent); // form 1`
- `long TestGetWaitLinCSErrorData (dword index, linCSError apEvent); // form 2`

## Description

Retrieves the data of a checksum error triggered by the last wait instruction. The second function can only be used for "joined events". The number of the "joined event" (return value of "testJoin...") is here being used as an index.

## Parameters

- **apEvent**: Data structure with the checksum error data.
- **index**: Number of the "joined event" corresponds with the return value of "testJoin...".

## Return Values

- **0**: Data access was successful
- **-1**: Data access failed – the last wait function was not triggered by a checksum error

## Example

```plaintext
testcase tcTFS_linCSError ()
{
    linCSError linCSErrorData;
    if (testWaitForLinCSError(5000) == 1)
    {
        if (testGetWaitLinCSErrorData(linCSErrorData) == 0)
        {
            testStep("Evaluation", "LIN CS Error event occurred for FrameId=0x%X", linCSErrorData.ID);
        }
    }
}
```

[TestJoinLinCSErrorEvent](CAPLfunctionTestJoinLinCsErrorEvent.md) • [TestWaitForLinCSError](CAPLfunctionTestWaitForLinCsError.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)