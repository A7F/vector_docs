[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForFrFrame.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForFrFrame**

# TestWaitForFrFrame

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForFrFrame (dbFrFrame aFrame, dword aTimeout);`
- `long TestWaitForFrFrame (dword aSlotId, dword aBaseCycle, int aCycleRepetition, dword aChannelMask, dword aTimeout);`
- `long TestWaitForFrFrame (dword aTimeout);`

## Description

Waits for the occurrence of the valid specified FlexRay frame. Should the frame not occur before the expiration of the time `aTimeout`, the wait condition is resolved nevertheless. When no frame is specified the wait condition is resolved on any valid FlexRay frame.

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aFrame**: Frame to be awaited as it is defined in the database.
- **aSlotId**: Numeric slot identifier. Value range: 1...2047
- **aBaseCycle**: Numeric base cycle. This value must be less than the repetition factor. Together with the repetition factor this value determines the "Cycle Multiplexing". Value range: 0...63
- **aCycleRepetition**: Cycle repetition factor. Together with the base cycle this value determines the "Cycle Multiplexing". Value has to be a power to 2 (1, 2, 4, 8, 16, 32 or 64).
- **aChannelMask**: Channel of the transmission message. Values:
  - 1: Channel A
  - 2: Channel B
  - 3: Channel A+B
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

The following test program waits for the occurrence of one of two frames. It is assumed that the database defines the frames Sync_Message_1_Ch_A and Sync_Message_2_Ch_A on the cluster FlexRay A.

```plaintext
variables
{
    dword gBusContextFr1;
    long resTestWaitFor, resTestGetData, resTestJoin;
    dword timeToWait = 10; // in ms
}
void InitBusContext ()
{
    gBusContextFr1 = getBusNameContext("FlexRay A");
    SetBusContext(gBusContextFr1);
}
testcase WaitForJoinedFrFrames_Any()
{
    FrFrame Sync_Message_1_Ch_A frTest1;
    FrFrame Sync_Message_2_Ch_A frTest2;
    InitBusContext();
    // join events
    {
        TestStepPass("Call TFS function", "TestJoinFrFrameEvent(Sync_Message_1_Ch_A) for (SlotId=%d, BaseCycle=%d, Repetition=%d)",
                     frTest1.FR_SlotID, frTest1.FR_CycleOffset, frTest1.FR_CycleRepetition);
        resTestJoin = TestJoinFrFrameEvent(Sync_Message_1_Ch_A);
        if (resTestJoin <= 0)
        {
            TestStepFail("Join condition", "resTestJoin = %d, Failure on joining symbolic event", resTestJoin);
            return;
        }
        else
        {
            TestStepPass("Join condition", "Joining symbolic event ok. Event number = %d", resTestJoin);
        }
        TestStepPass("Call TFS function", "TestJoinFrFrameEvent(SlotId=%d, BaseCycle=%d, Repetition=%d,...)",
                     frTest2.FR_SlotID, frTest2.FR_CycleOffset, frTest2.FR_CycleRepetition);
        resTestJoin = TestJoinFrFrameEvent(frTest2.FR_SlotID, frTest2.FR_CycleOffset, 
                                           frTest2.FR_CycleRepetition, frTest2.FR_ChannelMask);
        if (resTestJoin <= 0)
        {
            TestStepFail("Join condition", "resTestJoin = %d, Failure on joining raw event", resTestJoin);
            return;
        }
        else
        {
            TestStepPass("Join condition", "Joining raw event ok. Event number = %d", resTestJoin);
        }
    }
    TestStepPass("Call TFS function", "TestWaitForAnyJoinedEvent(timeout = %d)", timeToWait);
    // wait for any event
    resTestWaitFor = TestWaitForAnyJoinedEvent(timeToWait);
    if (resTestWaitFor > 0) // Resume due to event occurred
    {
        TestStepPass("Call TFS function", "TestGetWaitFrFrameData(resTestWaitFor=%d, frTest)", resTestWaitFor);
        // extract resume event's data
        resTestGetData = TestGetWaitFrFrameData(resTestWaitFor, frTest1);
        if (0 != resTestGetData)
        {
            TestStepFail("Data extraction", "resTestGetData = %d, Data access to data of event %d could not be executed!", resTestGetData, resTestWaitFor);
        }
        else
        {
            TestStepPass("Data extraction", "Data of event %d succefully extracted. SlotId=%d", resTestWaitFor, frTest1.FR_SlotID);
        }
    }
    else
    {
        TestStepFail("Wait condition", "resTestWaitFor = %d, Waiting for any of joined events during %d [ms] failed!", resTestWaitFor, timeToWait);
    }
}
```

[TestGetWaitFrFrameData](CAPLfunctionTestGetWaitFrFrameData.md) • [TestJoinFrFrameEvent](CAPLfunctionTestJoinFrFrameEvent.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)