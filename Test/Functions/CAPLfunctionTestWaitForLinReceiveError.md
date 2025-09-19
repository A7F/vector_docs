[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForLinReceiveError.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForLinReceiveError

# TestWaitForLinReceiveError

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForLinReceiveError (dword aFrameId, dword aTimeout);
long TestWaitForLinReceiveError (dword aTimeout);
```

## Description

Waits for the occurrence of LIN Receive Error event. Should the event not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrameId**: Numeric ID of a frame whose Receive Error should be awaited. Default value: wait for any ID
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
testcase tcTFS_linReceiveErrorEvent ()
{
    linReceiveError linReceiveErrorData;

    if (testWaitForLinReceiveError(5000) == 1)
    {
        if (TestGetWaitLinReceiveErrData(linReceiveErrorData) == 0)
        {
            testStep("Evaluation", "LIN Receive Error event occurred for FrameId=0x%X", linReceiveErrorData.ID);
        }
    }
}
```

[TestGetWaitLinReceiveErrData](CAPLfunctionTestGetWaitLinReceiveErrData.md) • [TestJoinLinReceiveErrorEvent](CAPLfunctionTestJoinLinReceiveErrorEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
