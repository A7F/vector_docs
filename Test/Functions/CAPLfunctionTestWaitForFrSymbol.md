# TestWaitForFrSymbol

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForFrSymbol (dword aTimeout);`
- `long TestWaitForFrSymbol (dword aSymbolType, dword aChannelMask, dword aTimeout);`

## Description

Waits for the occurrence of a FlexRay symbol on the bus. Should the symbol not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aTimeout**: Maximum time that should be waited [ms]. (Transmission of 0: no timeout controlling)
- **aSymbolType**: Identifies the type of symbol the function will wait for.
  - `0`: unknown
  - `1`: CAS
  - `2`: MTS
  - `3`: Wakeup
- **aChannelMask**: Identifies the FlexRay channel of the communication controller. A value of 1 will wait for the symbol on channel A, 2 will wait for it on channel B and 3 on any channel (A/B).

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

**Note:** If you want to wait for the reception or transmission of a **wake-up pattern** you have to use [TestWaitForFrPOCState](CAPLfunctionTestWaitForFrPOCState.md).

The following test program waits for the occurrence of different POC state events and symbols on one FlexRay bus.

```c
variables
{
  char bus1[20] = "FlexRay_1";
  char bus2[20] = "FlexRay_2";
  msTimer actionTimer;
  int  gAction = 0;
  const int gActionDelay = 52;   // [ms]
  const int gTimeout     = 300;  // [ms]
  const int gExtTimeout  = 2700; // [ms] to be waited additionally after cluster wake-up
  const int cPossibleWakeupDelay = 1500; // [ms] to be waited after possible cluster wake-up
  const int cWakeupDelay = 1500; // [ms] to be waited after cluster wake-up
  BYTE gSta1Id      = 5;  // slot ID for frame to send
  BYTE gSta1Flags   = 16; // event-triggered
  BYTE gSta1Dlc     = 4;  // bytes
  BYTE gSta1Chan    = 3;  // send on channel A+B
  BYTE gSta1Base    = 0;  // base cycle
  BYTE gSta1Rep     = 1;  // cycle repetition
}

testcase GoodCheckFlexRayWaitForSymbol_1 ()
{
  long result;
  FrSymbol frSymbolData;

  TestStepPass("Library: FrTFS_Wait_Symbol_POC.can", "Testcase: WaitForSymbol_Any");
  InitBusContext();
  _wakeupCluster(1);
  TestStep("Wait","waiting to assure running cluster...");
  TestWaitForTimeout(cPossibleWakeupDelay);
  TestStep("Prepare","Defining 'FlexRay symbol to be sent' action and triggering timer...");
  gAction = 1;
  actionTimer.set(gActionDelay);
  TestStep("Wait","Waiting for any FlexRay symbol...");
  TestStepPass("Call TFS function", "TestWaitForFrSymbol(timeout=%d)", gTimeout+1000);

  // The real test to be checked:
  result = TestWaitForFrSymbol(gTimeout+1000);
  if (result == 0)
  {
    TestStepFail("Timeout Occurred");
  }
  else if (result == -1)
  {
    TestStepFail("General Error");
  }
  else if (result == -2)
  {
    TestStepFail("Constraint Violation");
  }
  else
  {
    TestStepPass("Any FlexRay symbol successfully received!");
    TestStepPass("Call TFS function", "TestGetWaitFrSymbolData(frSymbolData)");
    // Test for data extraction:
    result = TestGetWaitFrSymbolData(frSymbolData);
    if (0 != result)
    {
      TestStepFail("Data extraction", "result = %d, Data access could not be executed.", result);
    }
    else
    {
      TestStepPass("Data extraction", "Data extraction works fine. Symbol=%d", frSymbolData.FR_Symbol);
    }
  }
}
```

[More Information](CAPLfunctionTestGetWaitFrSymbolData.md) • [TestJoinFrSymbolEvent](CAPLfunctionTestJoinFrSymbolEvent.md)
