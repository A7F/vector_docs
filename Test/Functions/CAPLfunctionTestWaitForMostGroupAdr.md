# TestWaitForMostGroupAdr

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long TestWaitForMostGroupAdr(long aValue, unsigned long aTimeout);
```

## Description

The function waits for the expiration of the time `aTimeout` for the occurrence of the MOST event of a change of the own group address.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aValue**: Expected value of the group address that should be in the MOST event.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring)

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: Resume based on Constraint Violation
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostNodeAdr](CAPLfunctionTestWaitForMostNodeAdr.md) • [TestWaitForMostMPR](CAPLfunctionTestWaitForMostMPR.md) • [TestWaitForMostNPR](CAPLfunctionTestWaitForMostNPR.md) • [TestWaitForMostSBC](CAPLfunctionTestWaitForMostSBC.md) • [TestWaitForMostNetState](CAPLfunctionTestWaitForMostNetState.md)
