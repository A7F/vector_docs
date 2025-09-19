[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForFrPDU.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForFrPDU

# TestWaitForFrPDU

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForFrPDU (dbFrPDU aPDU, dword aTimeout);`
- `long TestWaitForFrPDU (char aPDUName[], dword aTimeout);`
- `long TestWaitForFrPDU (dword aTimeout);`

## Description

Waits for the occurrence of the specified FlexRay PDU. Should the PDU not occur before the expiration of the time **aTimeout**, the wait condition is resolved nevertheless.

When no PDU is specified the wait condition is resolved on any FlexRay PDU.

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aPDU**: PDU to be awaited as it is defined in the database.
- **aPDUName**: Name of a PDU to be awaited as it is defined in the database.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout controlling)

## Return Values

- **-6**: Parse error, PDU is specified as string, but the name cannot be resolved
- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

The following test program waits for the occurrence of one of two PDUs. It is assumed that the database defines the PDUs PDU_NMF_NODE_C and PDU_IN_CYCLE_REPETITION on the cluster FlexRay PDU.

```plaintext
variables
{
   dword gBusContextFr;
   long resTestWaitFor, resTestGetData, resTestJoin;
   dword timeToWait  = 10; // in ms
}
void InitBusContext ()
{
   gBusContextFr = getBusNameContext("FlexRay_PDU");
   SetBusContext(gBusContextFr);
}
testcase WaitForJoinedFrPDUs_Any()
{
   FrPDU frTest;
   TestStepPass("Library: WaitForFrPDU.can", "Testcase: WaitForJoinedFrPDUs_Any");
   InitBusContext();
   // join events
   {
      TestStepPass("Call TFS function", "TestJoinFrPDUEvent(name=PDU_IN_CYCLE_REPETITION)");
      resTestJoin = TestJoinFrPDUEvent(PDU_IN_CYCLE_REPETITION);
      if (resTestJoin <= 0)
      {
         TestStepFail("Join condition", "resTestJoin = %d, Failure on joining symbolic event", resTestJoin);
         return;
      }
      else
      {
         TestStepPass("Join condition", "Joining symbolic event ok. Event number = %d", resTestJoin);
      }
      TestStepPass("Call TFS function", "TestJoinFrPDUEvent(name=PDU_NMF_NODE_C)");
      resTestJoin = TestJoinFrPDUEvent(PDU_NMF_NODE_C);
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
   // wait for all events
   TestStepPass("Call TFS function", "TestWaitForAnyJoinedEvent(timeout=%d)", timeToWait);
   resTestWaitFor = TestWaitForAnyJoinedEvent(timeToWait);
   if (resTestWaitFor > 0) // Resume due to event occurred
   {
      TestStepPass("Wait condition", "Waiting for any event is ok. Resume event number = %d", resTestWaitFor);
      TestStepPass("Call TFS function", "TestGetWaitFrPDUData(index=%d)", resTestWaitFor);
      
      // extract resume event's data
      resTestGetData = TestGetWaitFrPDUData(resTestWaitFor, frTest);
      if (0 != resTestGetData)
      {
         TestStepFail("Data extraction", "resTestGetData = %d, Data access to data of event %d could not be executed!", resTestGetData, resTestWaitFor);
      }
      else
      {
         TestStepPass("Data extraction", "Data of event %d successfully extracted. SlotId=%d", resTestWaitFor, frTest.FR_SlotID);
      }
   }
   else
   {
      TestStepFail("Wait condition", "resTestWaitFor = %d, Waiting for any of joined events failed!", resTestWaitFor);
   }
}
```

[TestGetWaitFrPDUData](CAPLfunctionTestGetWaitFrPDUData.md) • [TestJoinFrPDUEvent](CAPLfunctionTestJoinFrPDUEvent.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
