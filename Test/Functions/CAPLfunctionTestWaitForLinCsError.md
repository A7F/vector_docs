# TestWaitForLinCSError

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TestWaitForLinCSError(dword aTimeout);
long TestWaitForLinCSError(dword aFrameId, dword aTimeout);
```

## Description

Waits for a checksum error for the specified amount of time.

**Note**  
Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. Transmission of 0: no timeout controlling.
- **aFrameId**: Frame identifier

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, e.g., functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

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

[TestGetWaitLinCSErrorData](CAPLfunctionTestGetWaitLinCsErrData.md) • [TestJoinLinCSErrorEvent](CAPLfunctionTestJoinLinCsErrorEvent.md)
