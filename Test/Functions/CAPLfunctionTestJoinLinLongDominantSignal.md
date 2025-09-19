[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinLinLongDominantSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinLinLongDominantSignal

# TestJoinLinLongDominantSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long TestJoinLinLongDominantSignal ()
```

## Description

Completes the current set of **joined events** with the transmitted event. This function does not wait.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

—

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
testcase tcTFS_waitForLINHeader(int frameId)
{
   long eventIndex;
   testJoinLinHeaderEvent(frameId);
   testJoinLinLongDominantSignal();
   testJoinLinSyncErrorEvent();
   eventIndex = testWaitForAnyJoinedEvent(5000);
   switch (eventIndex)
   {
      case 1:
         testStepPass("Validation", "LIN Header for FrameId=0x%X occurred", frameId);
         break;

      case 2:
         testStepFail("Validation", "LIN long dominant signal occurred");
         break;

      case 3:
         testStepFail("Validation", "LIN Sync error occurred");
         break;

      default:
         testStepFail("Validation", "Internal error! Unexpected event (return code %d) on waiting for any LIN event", eventIndex);
   }
}
```

[TestGetWaitLinLongDominantSignalData](CAPLfunctionTestGetWaitLinLongDominantSignalData.md) • [TestWaitForLinLongDominantSignal](CAPLfunctionTestWaitForLinLongDominantSignal.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
