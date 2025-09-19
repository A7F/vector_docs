[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostAllBypass.md)

**CAPL Functions » Test Feature Set » TestWaitForMostAllBypass**

# TestWaitForMostAllBypass

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
long TestWaitForMostAllBypass(long aValue, unsigned long aTimeout);
```

## Description

Use this function to determine whether the bypass on the MOST hardware connected to the channel has been set to the specified condition within the waiting time. The wait point is only triggered if a change to this condition takes place.

The following can be entered as possible condition values: 1 for closed bypass and 0 for open bypass. In the case of a closed bypass, the MOST device cannot be seen by the other devices in the loop.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aValue**: Bypass condition that should be waited for. Possible values are:
  - `1`: Bypass is closed
  - `0`: Bypass is opened

- **aTimeout**: Maximum wait time [ms]
  - (Transmission of 0: no timeout controlling; test module waits infinitely long)

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[Related Topics: TestWaitForMostAsRegistry](CAPLfunctionTestWaitForMostAsRegistry.md) • [TestWaitForMostNodeAdr](CAPLfunctionTestWaitForMostNodeAdr.md) • [TestWaitForMostGroupAdr](CAPLfunctionTestWaitForMostGroupAdr.md) • [TestWaitForMostNPR](CAPLfunctionTestWaitForMostNPR.md) • [TestWaitForMostMPR](CAPLfunctionTestWaitForMostMPR.md) • [TestWaitForMostSBC](CAPLfunctionTestWaitForMostSBC.md) • [TestWaitForMostNetState](CAPLfunctionTestWaitForMostNetState.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
