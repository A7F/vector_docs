# TestWaitForMostNetState

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```c
long TestWaitForMostNetState(long aOldState, long aNewState, unsigned long aTimeout);
```

## Description

The function waits until the expiration of the time **aTimeout** for a transfer of the MOST NetState from the state **aOldState** into the state **aNewState**.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aOldState**: Expected initial state of the NetState. The following values are allowed:
  - `0`: MostNetState_Undefined
  - `2`: MostNetState_PowerOff
  - `3`: MostNetState_NetInterfaceInit
  - `4`: MostNetState_ConfigNotOk
  - `5`: MostNetState_ConfigOk
  - `-1`: Wildcard, any NetState state

- **aNewState**: Expected new state of the NetState. The value range corresponds to that of aOldState Parameters.

- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring)

## Return Values

- `-2`: Resume based on Constraint Violation
- `-1`: General error e.g. the functionality is not available
- `0`: Resume based on Timeout
- `1`: Resume based on occurred event

## Example

—

[TestWaitForMostNodeAdr](CAPLfunctionTestWaitForMostNodeAdr.md) • [TestWaitForMostGroupAdr](CAPLfunctionTestWaitForMostGroupAdr.md) • [TestWaitForMostMPR](CAPLfunctionTestWaitForMostMPR.md) • [TestWaitForMostNPR](CAPLfunctionTestWaitForMostNPR.md) • [TestWaitForMostSBC](CAPLfunctionTestWaitForMostSBC.md)
