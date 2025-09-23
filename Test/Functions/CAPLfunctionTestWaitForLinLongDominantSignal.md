# TestWaitForLinLongDominantSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestWaitForLinLongDominantSignal (dword aTimeout);
```

## Description

Waits for the occurrence of a LIN long dominant signal. Should the frame not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```c
testcase tcTFS_linLongDominantSignal ()
{
    linLongDominantSignal linLongDominantSignal;
    if (testWaitForLinLongDominantSignal (5000) == 1)
    {
        if (testGetWaitLinLongDominantSignalData(linLongDominantSignal) == 0)
        {
            testStep("Evaluation", "LIN LongDominantSignal event occurred. Signal length is %d ns", linLongDominantSignalData.length_ns);
        }
    }
}
```

[TestGetWaitLinLongDominantSignalData](CAPLfunctionTestGetWaitLinLongDominantSignalData.md) • [TestJoinLinLongDominantSignal](CAPLfunctionTestJoinLinLongDominantSignal.md)
