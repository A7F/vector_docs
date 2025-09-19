[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Test/Functions/CAPLfunctionTestWaitForMostSBC.md)

[CAPL Functions](../../CAPLfunctions.md) » [Test Feature Set](../CAPLfunctionsTFSOverview.md) » TestWaitForMostSBC

# TestWaitForMostSBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long TestWaitForMostSBC(long aValue, unsigned long aTimeout);
```

## Description

The function waits for the expiration of the time **aTimeout** for the occurrence of the MOST event of a change of the value of the Synchronous Bandwidth Control (SBC) Register.

**Note:** Consider to set always the appropriate bus context in a multibus environment before the function is called. Further information on site [MultiBus Environment](../../../Shared/CAPL/General/TestMultiBusEnvironment.md).

## Parameters

- **aValue**: Expected value of the Synchronous Bandwidth Control Registers that should be in the MOST event. The specification -1 (wildcard) stands for any values.
- **aTimeout**: Maximum time that should be waited [ms] (Transmission of 0: no timeout monitoring)

## Return Values

- **-2**: Resume based on Constraint Violation
- **-1**: General error e.g. the functionality is not available
- **0**: Resume based on Timeout
- **1**: Resume based on occurred event

## Example

—

[TestWaitForMostNodeAdr](CAPLfunctionTestWaitForMostNodeAdr.md) • [TestWaitForMostGroupAdr](CAPLfunctionTestWaitForMostGroupAdr.md) • [TestWaitForMostNPR](CAPLfunctionTestWaitForMostNPR.md) • TestWaitForMostSBC • [TestWaitForMostNetState](CAPLfunctionTestWaitForMostNetState.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
