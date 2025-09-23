# TestWaitForJ1939DTC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TestWaitForJ1939DTC (dword sourceAddress, Message message, dword spn, dword timeout); // form 1`
- `long TestWaitForJ1939DTC (dword sourceAddress, dword pgn, dword spn, dword timeout); // form 2`
- `long TestWaitForJ1939DTC (Node node, Message message, dword spn, dword timeout); // form 3`
- `long TestWaitForJ1939DTC (Node node, dword pgn, dword spn, dword timeout); // form 4`
- `long TestWaitForJ1939DTC (dword sourceAddress, Message message, dword spn, word fmi, word oc, dword timeout); // form 5`
- `long TestWaitForJ1939DTC (dword sourceAddress, dword pgn, dword spn, word fmi, word oc, dword timeout); // form 6`
- `long TestWaitForJ1939DTC (Node node, Message message, dword spn, word fmi, word oc, dword timeout); // form 7`
- `long TestWaitForJ1939DTC (Node node, dword pgn, dword spn, word fmi, word oc, dword timeout); // form 8`

## Description

Waits until a defined Parameter Group and a defined Diagnostic Trouble Code (DTC) is received or a timeout occurred.

The affected message (specified by the Parameter Group number **pgn** or the database object **message**) must be able to contain a DTC, so only this parameter groups are allowed: DM1, DM2, DM4, DM6, DM12, DM23, DM24, DM27, DM28, DM31, DM35 and DM41-DM54.

To get the message content of the parameter group which triggered the wait condition you can use the function [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md).

**Note**: Dependent on the used parameter type the appropriate bus context in a multibus environment has only to be set before the function is called if the corresponding database object will be ambiguous. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **message**: Message containing the specified DTC. Must be a J1939 Parameter Group.
- **pgn**: Parameter Group Number (with data page) of the message containing the specified DTC.
- **node**: Sender of the message containing the specified DTC.
- **sourceAddress**: Source address of the message containing the specified DTC. `0xFFFFFFFF` if source address is to be ignored.
- **spn**: Suspect Parameter Number of the specified DTC. `0xFFFFFFFF` if **spn** is to be ignored.
- **fmi**: Failure Mode Identifier of the specified DTC. `0xFFFF` if **fmi** is to be ignored.
- **oc**: Occurrence Counter of the specified DTC. `0xFFFF` if **oc** is to be ignored.
- **timeout**: Maximum time to wait [ms]. **0** if timeout is to be ignored.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

**Example 1**

```plaintext
long result;

// wait for the occurrence of DTC with SPN=96 and FMI=12 within message DM1 (pgn=0xFECA) from node with address=0x2
result = TestWaitForJ1939DTC(0x2, DM01.pgn, 96, 12, 0xFFFF, 2000);

// wait for the occurrence of DTC with SPN=98765 and OC=1 within message DM2 (pgn=0xFECB) from node with address=0x3
result = TestWaitForJ1939DTC(0x3, 0xFECB, 98765, 0xFFFF, 1, 2000);

// wait for the occurrence of DTC with OC=10 within message DM35 (pgn=0x9F00) from any node
result = TestWaitForJ1939DTC(0xFFFFFFFF, 0x9F00, 0xFFFFFFFF, 0xFFFF, 10, 2000);
```

**Example 2**

```plaintext
long result;
pg DM01 pgDM01;

// wait for the occurrence of DTC with SPN=96 and FMI=12
// within message DM1 (pgn=0xFECA) from node with address=0x2
result = TestWaitForJ1939DTC(0x2, DM01.pgn, 96, 12, 0xFFFF, 2000);
if (result == 1)
{
  // validate lamp status of DM01
  result = TestGetWaitJ1939PGData(pgDM01);
  if (result == 0)
  {
    if (pgDM01.ProtectLampStatus != 1)
    {
      testStepFail("Validation", "ProtectLampStatus of DM01 is not 1");
    }
    else
    {
      testStepPass("Validation", "DM01 with expected DTC (SPN 96, FMI12)  and  ProtectLampStatus 1 occurred");
    }
  }
  else
  {
    testStepFail("Validation", "Failed to get data of DM01 (return code of TestGetWaitJ1939PGData: %d)", result);
  }
}
else if (result == 0)
{
  testStepFail ("Validation", "DM01 with expected DTC is not received within 2000 ms");
}
else
{
  testStepFail ("Validation", "TestWaitForJ1939PG(0xEA00, 0x01, 0xAA, 2000): unexpected error %i", result);
}
```

[**TestJoinJ1939DTCEvent**](CAPLfunctionTestJoinJ1939DTCEvent.md) • [**TestGetWaitJ1939PGData**](CAPLfunctionTestGetWaitJ1939PGData.md) • [**TestWaitForJ1939PG**](CAPLfunctionTestWaitForJ1939PG.md)
