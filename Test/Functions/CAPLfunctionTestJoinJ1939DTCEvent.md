[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestJoinJ1939DTCEvent.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestJoinJ1939DTCEvent

# TestJoinJ1939DTCEvent

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestJoinJ1939DTCEvent (dword sourceAddress, Message message, dword spn); // form 1`
- `long TestJoinJ1939DTCEvent (dword sourceAddress, dword pgn, dword spn); // form 2`
- `long TestJoinJ1939DTCEvent (Node node, Message message, dword spn); // form 3`
- `long TestJoinJ1939DTCEvent (Node node, dword pgn, dword spn); // form 4`
- `long TestJoinJ1939DTCEvent (dword sourceAddress, Message message, dword spn, word fmi, word oc); // form 5`
- `long TestJoinJ1939DTCEvent (dword sourceAddress, dword pgn, dword spn, word fmi, word oc); // form 6`
- `long TestJoinJ1939DTCEvent (Node node, Message message, dword spn, word fmi, word oc); // form 7`
- `long TestJoinJ1939DTCEvent (Node node, dword pgn, dword spn, word fmi, word oc); // form 8`

## Description

Completes the current set of joined events with the additional Diagnostic Trouble Code (DTC) event – transmitted with one of the J1939 diagnostic messages. This function does not wait. For waiting, either [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md) or [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) should be used depending on the requirement.

The affected message (specified by the Parameter Group number **pgn** or the database object **message**) must be able to contain a DTC, so only this parameter groups are allowed: DM1, DM2, DM4, DM6, DM12, DM23, DM24, DM27, DM28, DM31, DM35 and DM41-DM54.

To get the message content of a Parameter Group which triggered a wait condition you can use function [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md).

**Note:** Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **message**: Message containing the specified DTC. Must be a J1939 Parameter Group.
- **pgn**: Parameter Group Number (with data page) of the message containing the specified DTC.
- **node**: Sender of the message containing the specified DTC.
- **sourceAddress**: Source address of the message containing the specified DTC. `0xFFFFFFFF` if source address is to be ignored.
- **spn**: Suspect Parameter Number of the specified DTC. `0xFFFFFFFF` if **spn** is to be ignored.
- **fmi**: Failure Mode Identifier of the specified DTC. `0xFFFF` if **fmi** is to be ignored.
- **oc**: Occurrence Counter of the specified DTC. `0xFFFF` if **oc** is to be ignored.

## Return Values

- **-3**: Join error
- **-1**: General error, for example, functionality is not available
- **> 0**: Number of the joined event

## Example

```plaintext
testcase tcWaitForOneOfDTCs(dword sourceAddress)
{
  long eventIndex;
  dword sa = 0x1;
  pg DM12 pgDM12;

  // All DTCs are transmitted with the message DM12 (pgn = 0xFED4).

  // DTC Condition 1: spn = 111, fmi = 12, oc to be ignored
  TestJoinJ1939DTCEvent (sourceAddress, DM12.pgn, 111, 12, 0xFFFF);

  // DTC Condition 2: spn = 222, fmi to be ignored, oc = 5
  TestJoinJ1939DTCEvent (sourceAddress, DM12.pgn, 222, 0xFFFF, 5);

  // DTC Condition 3: spn = 333, fmi and oc to be ignored
  TestJoinJ1939DTCEvent (sourceAddress, DM12.pgn, 333, 0xFFFF, 0xFFFF);

  eventIndex = testWaitForAnyJoinedEvent(5000);
  switch (eventIndex)
  {
    case 1:
      testStepPass("Validation", "DTC with spn=111 and fmi=12 occurred");
      if (testGetWaitJ1939PGData(eventIndex, pgDM12) == 0)
      {
        // validate data of received DM12 via pgDM12
      }
      break;

    case 2:
      testStepPass("Validation", "DTC with spn=222 and oc=5 occurred");
      if (testGetWaitJ1939PGData(eventIndex, pgDM12) == 0)
      {
        // validate data of received DM12 via pgDM12
      }
      break;

    case 3:
      testStepPass("Validation", "DTC with spn=333 occurred");
      if (testGetWaitJ1939PGData(eventIndex, pgDM12) == 0)
      {
        // validate data of received DM12 via pgDM12
      }
      break;

    default:
      testStepFail("Validation", "Unexpected event or timeout (return code of testWaitForAnyJoinedEvent: %d)", eventIndex);
      break;
  }
}
```

[TestWaitForJ1939DTC](CAPLfunctionTestWaitForJ1939DTC.md) • [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md) • [TestWaitForAnyJoinedEvent](CAPLfunctionTestWaitForAnyJoinedEvent.md) • [TestWaitForAllJoinedEvents](CAPLfunctionTestWaitForAllJoinedEvents.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
