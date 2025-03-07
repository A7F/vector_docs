[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForJ1939DmWithoutSPN.md)

**CAPL Functions** » **Test Feature Set** » **TestWaitForJ1939DmWithoutSPN**

# TestWaitForJ1939DmWithoutSPN

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long testWaitForJ1939DmWithoutSPN (dword sourceAddress, dword pgn, dword spn, dword timeout); // form 1
long testWaitForJ1939DmWithoutSPN (dword sourceAddress, dword pgn, dword spn, word fmi, word oc, dword timeout); // form 2
```

## Description

Waits until a defined Parameter Group and a defined Diagnostic Trouble Code (DTC) disappears within a given timeout.

The affected diagnostic message (specified by the Parameter Group number **pgn**) must be able to contain a DTC, so only these parameter groups are allowed: DM1, DM2, DM4, DM6, DM12, DM23, DM24, DM27, DM28, DM31, DM35 and DM41-DM54.

To get the message content of the parameter group which triggered the wait condition you can use the function [TestGetWaitJ1939PGData](CAPLfunctionTestGetWaitJ1939PGData.md).

## Parameters

- **sourceAddress**: Source address of the message containing the specified DTC.
- **pgn**: Parameter Group Number (with data page) of the Diagnostic Message.
- **spn**: Suspect Parameter Number of the specified DTC. `0xFFFFFFFF` if spn is to be ignored.
- **fmi**: Failure Mode Identifier of the specified DTC. `0xFFFF` if **fmi** is to be ignored.
- **oc**: Occurrence Counter of the specified DTC. `0xFFFF` if **oc** is to be ignored.
- **timeout**: Maximum time to wait [ms]. **0** if timeout is to be ignored.

## Return Values

- **-2**: Resume due to constraint violation
- **-1**: General error, for example, functionality is not available
- **0**: Resume due to timeout
- **1**: Resume due to event occurred

## Example

```plaintext
char kBusContextJ1939_1[100] = "J1939_1";
export testfunction TestWaitForDtcCycle(long sa, dword pgn, dword spn, dword timeoutToAppear, dword timeoutToDisappear)
{
  long result;

  testStepPass();
  setBusContext( getBusNameContext(kBusContextJ1939_1) ); // Set the channel, the test function is applied to

  // Wait for the given SPN
  result = TestWaitForJ1939DTC(sa, pgn, spn, timeoutToAppear );
  if (result != 1)
  {
    // SPN did not occur - Test failed
    TestStepFail ("DTC did not occur");
  }
  // Expect the SPN to be dismissed.
  result = testWaitForJ1939DmWithoutSPN(sa, pgn, spn, timeoutToDisappear);
  if (result != 1)
  {
    // SPN is still sent - Test failed
    TestStepFail ("SPN is still part of the given DM");
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)