# TestWaitForLinHeader

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForLinHeader (dbMsg aFrame, dword aTimeout);`
- `long TestWaitForLinHeader (dword aFrameId, dword aTimeout);`
- `long TestWaitForLinHeader (dword aTimeout);`

## Description

Waits for the Header occurrence of the specified LIN frame. Should the header not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

When no frame is specified the wait condition is resolved on any LIN header.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrame**: Frame whose header should be awaited.
- **aFrameId**: Numeric ID of a frame whose header should be awaited.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```plaintext
testcase tcTFS_linHdrEvent ()
{
   linheader  linHeaderData;

   if (testWaitForLinHeader(5000) == 1)
   {
      if (TestGetWaitLinHdrData(linHeaderData) == 0)
      {
         testStep("Evaluation", "LIN Header event occurred for FrameId=0x%X", linHeaderData.ID);
      }
   }
}
```

[TestGetWaitLinHdrData](CAPLfunctionTestGetWaitLinHdrData.md) • [TestJoinLinHeaderEvent](CAPLfunctionTestJoinLinHeaderEvent.md) • [linHeader selectors](../../LIN/Selectors/CAPLfunctionLINHeader.md)
