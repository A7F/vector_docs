[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostAsRegistry.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostAsRegistry

# TestWaitForMostAsRegistry

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long TestWaitForMostAsRegistry(long aRegistry, unsigned long aTimeout);
```

## Description

The function waits for the specified time period for any change to a registry in the application socket.

**Note**: Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aRegistry**: The following values are permitted:
  - `1`: Wait for changes in the local registry
  - `2`: Wait for changes in the global registry
  - `-1`: Wait for changes in all registries

- **aTimeout**: Maximum time that should be waited [ms]
  - (Transmission of 0: no timeout monitoring; test module waits infinitely long)

## Return Values

- `-2`: Resume based on Constraint Violation
- `-1`: General error e.g. the functionality is not available
- `0`: Resume based on Timeout
- `1`: Resume based on occurred event

## Example

—

[TestWaitForMostNodeAdr](CAPLfunctionTestWaitForMostNodeAdr.md) • [TestWaitForMostGroupAdr](CAPLfunctionTestWaitForMostGroupAdr.md) • [TestWaitForMostNPR](CAPLfunctionTestWaitForMostNPR.md) • [TestWaitForMostMPR](CAPLfunctionTestWaitForMostMPR.md) • [TestWaitForMostSBC](CAPLfunctionTestWaitForMostSBC.md) • [TestWaitForMostNetState](CAPLfunctionTestWaitForMostNetState.md) • [TestWaitForMostAllBypass](CAPLfunctionTestWaitForMostAllBypass.md) • [Symbolic definition of MOST messages](../CAPLfunctionsTFSSymbolicMessageDefinition.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)